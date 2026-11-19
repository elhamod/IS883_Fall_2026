# IS883 Practice final exam: solutions

Try `Practice final exam.md` under exam conditions first. These are model answers: a full-credit answer makes the
same points, in your own words, within the question's sentence limit. Where more than one answer is acceptable, the
alternatives are listed.

---

## Part 1: Short questions

### Q1. More context, fewer examples

- **(a) Fewer.** Every time "out his wand" appears, "his wand" appears too, so a longer phrase can occur at most as
  often as the shorter one inside it, never more. ("Fewer or the same" is also correct.)
- **(b) Fewer.** The words that follow "pulled out his wand" are a subset of the words that follow "out his wand", so
  the list of different next words can only shrink. ("Fewer or the same" is also correct.)
- **(c) 1.0, and no, it is not reliable.** The model has seen the phrase once, so whatever came next that one time gets
  all the probability. That records what happened once, not how likely the word is in general.

The idea behind all three parts: more context makes the prediction more specific, but it rests on fewer examples.
A "fewer" with no reason earns no credit; the reason is the point of the question.

### Q2. What does this GPT-2 write?

**B.** The code builds the model from a configuration (`GPT2LMHeadModel(config)`) and never trains it or loads trained
weights with `from_pretrained`. Its weights are random, so every token is about equally likely, and it strings together
random pieces of words. A looks like n-gram output, C is what a trained GPT-2 writes, and D is wrong because an
untrained model can still generate; it just generates nonsense.

### Q3. Testing on a different author

**B. Much higher.** A model trained from scratch on one author's books learns that author's exact word sequences,
which a different author doesn't repeat, so the new text is far more surprising to it. A is the trap: being in the same
genre does not make the word sequences the same. C and D are wrong because new text is harder to predict, and a
perplexity of exactly 1 would mean perfect prediction.

### Q4. Will it fit?

| Model | Memory needed | Fits in 2.7 GB? |
|---|---|---|
| Llama 3.2 3B | about 6 GB (3 billion × 2 bytes) | does not fit |
| Llama 3.2 1B | about 2 GB | fits (barely; "does not fit" is also accepted if you point out the app itself needs memory too) |
| Qwen2.5 0.5B | about 1 GB | fits |

One way to make the 3B model fit: **quantize** it (for example, 4-bit weights need about 1.5 GB), or run it on a host
with more memory.

### Q5. Medical bot assumes "he"

- **Cause:** the model learned from text in which doctors are mostly "he", so "he" is the more likely next word. It
  fills the gap with the most common pattern, not with a fact.
- **Fix (without retraining):** in the system instruction, tell it not to assume the doctor's gender and to say "your
  doctor" or "they" unless the patient says otherwise; add a few examples (few-shot) that show the neutral wording.
- **Confirm:** run a fixed set of patient questions before and after the change, and count how often a gendered pronoun
  appears when none was given. Re-run it whenever the prompt or the model changes.

### Q6. The warranty answer

**D. Rebuild the vector database from the current manuals, and keep it updated.** The evidence rules out the other
causes:
- The answer matches the passage it cites, so the model did not make it up (this rules out A and C, which target
  hallucination).
- All 5 chunks came from the right manual, so retrieval worked; retrieving more (B) only returns more of the same
  manual.
- Ten identical answers rule out randomness.

The source itself is wrong: the database was built in January 2024 and still holds a manual that has since changed.

### Q7. Same prompt, new answer

**B. Google pointed `gemini-flash-latest` to a newer model.** Temperature 0 and a fixed seed repeat answers only while
the model stays the same. A name ending in "latest" is one the provider moves to each new model, so the model changed
under the same name. E is false for the same reason. A and D describe things that don't happen, and C is wrong because
each API call is independent: earlier calls don't fill this call's context window.

### Q8. Is chain of thought agentic?

**False.** Chain of thought is the model writing out reasoning text before it answers. An agent decides on actions and
takes them, such as calling tools, in a loop, and reacts to what comes back.

### Q9. What Gemini sees of a tool

**False.** Gemini sees only the function's name, its description (the docstring) and its argument types. The code
inside runs in the notebook, not in Gemini, and Gemini never reads it.

### Q10. Is the long chat the problem?

**A and D.**
- **D** (`/context`) measures how full the context window is.
- **A** tests whether the long chat is the cause: same question, fresh session, short summary, compare the answers.
- **B** asks the model to judge its own context, which it can't do reliably.
- **C** (temperature) and **F** (web search) change something else, so they tell you nothing about the context.
- **E** repeats the question in the same long session, so it can't separate the cause.

### Q11. It passed the online question set

Any two of these reasons:
- The collection has been public for years, so the model has probably seen it, and its answers in its training data.
- The questions are not your company's questions, and its answers are not your company's policies.
- A general question set doesn't test whether your retrieval finds the right policy document.

**Test it instead** with your own realistic customer questions and your own policies' answers. Include questions where
your policy differs from the industry norm: only those show whether the system used your documents.

### Q12. An agent wipes an inbox

**No.** A better model might make this less likely, but no model can guarantee it. Two choices made it possible:
- **The permission was too broad.** The agent could delete emails, and nothing in the software enforced the approval
  step. "Wait for my approval" was only a sentence in the conversation, which is a request, not a control.
- **That sentence was lost.** The real inbox was so large that the agent's context filled up and was summarized, and
  the instruction was dropped from the summary.

**What she should have done:**
- Give it read-only or archive-only access, which can be undone.
- Require a click in the app to approve each deletion.
- Test on a large copy of the inbox, not only a small one.

---

## Part 2: Essays

### Q13. Ship which version?

**(a) Cost per answer = tokens in × $0.10/1M + tokens out × $0.40/1M; per month = × 100,000.**

| | Version 1 | Version 2 | Version 3 |
|---|---|---|---|
| Per answer | 300 × 0.10/1M + 150 × 0.40/1M = $0.00009 | 9,000 × 0.10/1M + 200 × 0.40/1M = $0.00098 | 2,500 × 0.10/1M + 180 × 0.40/1M = $0.000322 |
| Per month | $9 | $98 | $32.20 |

**(b)** Version 3 is the only one that meets both limits: $32.20 against the $50 budget, and 1.8 seconds against the
2-second promise. You gain both, and give up some accuracy (4 of 5 runs right instead of 5 of 5). Version 2 is
defensible only if you argue for a bigger budget and slower answers. Version 1 is never acceptable: it is cheap and
fast but almost always wrong.

**(c)** Version 1 can only guess from its training data, which does not contain this company's policy. Versions 2 and
3 read the policy from the manual: their answers are grounded.

**(d)**
- **Cost:** $98 − $32.20 = **$65.80** a month.
- **Benefit:** Version 3 is wrong in 1 of 5 runs, so about 20% of 100,000 = 20,000 wrong answers a month, at $2 each:
  **$40,000** a month.
- **Cost-benefit ratio:** $40,000 ÷ $65.80 ≈ **608**.
- **ROI:** ($40,000 − $65.80) ÷ $65.80 ≈ **+60,700%**.

The token budget was the wrong limit to worry about: the extra tokens pay for themselves many times over. Version 2's
real obstacle is speed, at 3.1 seconds against the 2-second promise. A good answer ships Version 2 if the product team
can relax the speed promise (or the answer can be made faster), and otherwise ships Version 3 and explains the cost of
its errors.

### Q14. Same setup, five different runs

- **(a)** Run 3 wrote about five times as much and took about three times as long, then failed. It most likely rambled
  or reasoned down a wrong path. Read that run's log to see where it went wrong, and flag unusually long outputs
  automatically.
- **(b)** 18,100 ≈ 2 × 9,000, so the model most likely called the search tool twice and the manual sections were added
  twice. Cap the number of searches per answer, or reuse the first result.
- **(c)** The model samples its output, so even with nothing changed, each run comes out a little different.
- **(d)** The average of 4.8 seconds describes no actual run: most runs take about 3 seconds, and 1 in 5 took 5 to 10
  seconds. Users feel the slow runs, so plan on the worst case: here the maximum (9.8 seconds); with many runs, a high
  percentile such as the 95th. The median (3.1 seconds) is no better, because it hides the slow runs completely. Look
  into why the slow runs were slow instead of averaging them away.

### Q15. Tracing a RAG chatbot

| # | Who contacts whom | Request | Response |
|---|---|---|---|
| 1 | Browser → Streamlit app | The employee's question | (none) |
| 2 | App → Gemini API (embedding model, `gemini-embedding-001`) | The question text | One vector (the question's embedding) |
| 3 | App → vector database | That vector: "give me the k most similar chunks" | The k most similar handbook chunks |
| 4 | App → Gemini API (chat model) | System instruction ("answer only from these passages, cite them"), the retrieved chunks, the conversation so far, and the question | The answer, with citations |
| 5 | App → browser | The answer | (none) |

Key points:
- The question must be embedded with the **same embedding model** that embedded the handbook, or the similarity search
  is meaningless.
- The chat model never searches the database itself; the app does the retrieval.
- **If the handbook is updated,** the changed sections must be re-chunked, re-embedded and replaced in the vector
  database. Otherwise the bot keeps answering from the old version.

### Q16. Reverse-engineering an apartment assistant

- **(a)** Besides the two messages, the model saw instructions that were written ahead of time, not typed into the
  chat. These could be a **skill** (whose description matched "find an apartment", so its full instructions were
  loaded) or a **system instruction** (custom or project instructions). Either is correct. Those instructions are where
  the behaviour comes from: ask for budget, bedrooms and move-in date first; add fees to the rent; set aside listings
  without a price or photos ("Not checked"); use the table format; end with "My pick".
- **(b)** It uses a **listings connector** (an MCP server, such as a Zillow connector): `search_listings` fetches live
  listings, which the model can't know from training. The **walking time** is likely unreliable: nothing in the tool
  call asks for it, so unless a maps tool was connected, the model estimated it. The "rent + fees" sums are arithmetic
  done by the model, so they are usually right for two small numbers but not guaranteed.
- **(c)** **Not RAG in the course's sense.** The evidence is the tool call: it passes exact filters (`bedrooms=2`,
  `max_rent=3200`, `move_in`) and gets back structured records, which is a database query, not a similarity search over
  embedded text chunks. It is the same grounding idea, though: fresh data is fetched and put into the context. ("RAG in
  the broad sense, retrieve then generate" is also accepted if you point to the tool call and note there is no sign of
  embeddings.)
- **(d)** It refused because of a written rule such as "never contact landlords", in the skill or the system
  instruction, and probably also because no tool for sending messages is connected. The rule alone is not reliable: it
  is a sentence in the context, which other text can override or which can be dropped as the context fills. What makes
  the refusal reliable is that no contact tool exists, so it **cannot** send a message, whatever it is told.
