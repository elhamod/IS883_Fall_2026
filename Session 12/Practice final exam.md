# IS883 Practice final exam

This practice paper has the same format, length and question types as the final exam. Worked solutions are in `Practice final exam - solutions.md`; try the paper under exam conditions (90 minutes, closed book, calculator only) before you read them.

## Instructions

```
IS883 — Deploy Generative AI in Enterprise          Practice final exam
Fall 2026

Time: 90 minutes.  Total: 100 points.
Part 1: 12 short questions, 4 points each (48 points).
Part 2: 4 essay questions (52 points).
Closed book. No generative AI. Use Examplify's calculator for arithmetic.
Where a question says "Explain in one sentence," a correct choice with no explanation earns no credit.
Each written answer has a sentence limit in brackets. Multiple-choice and fill-in questions need no explanation
unless the question asks for one.
Select-all questions are scored per option: each correct tick earns credit, each wrong tick loses it. A question's
score never goes below 0.
Text past a question's sentence limit is not graded. Padding an answer with irrelevant material may lose points.
```

### Formulas you may use

| Term | Formula | Reading it |
|---|---|---|
| Cost of one answer | tokens × price per token, added up over each kind of token (input, output, thinking, …) | Prices are usually quoted per 1M tokens |
| **Break-even** | the time (or volume) at which total benefit = total cost | Sooner (or lower) is better |
| **ROI** (return on investment) | (benefit − cost) ÷ cost, over a stated period | Negative → not viable |
| **Cost-benefit ratio** | benefit ÷ cost, over a stated period | Below 1 → not viable |

---

## Part 1 — Short questions (4 points each)

### Q1. More context, fewer examples · short answer

A 5-gram model is trained on the seven *Harry Potter* novels (about a million words). For a phrase,
`show_next_words(model, phrase)` prints how many times the phrase appeared in the training text, how many different
words followed it, and each next word's probability: how often that word followed the phrase ÷ how often the phrase
appeared. A student runs it on a growing phrase:

```python
for context in ["wand", "his wand", "out his wand", "pulled out his wand"]:
    show_next_words(hp_model_5, context, how_many=5)
```

The phrase grows from one word ("wand") to four ("pulled out his wand"). Answer without seeing the output.

(a) As the phrase gets longer, how many times does it appear in the training text: more, fewer, or the same? Explain
why. [At most 2 sentences.]
(b) As the phrase gets longer, how many different words follow it in the training text: more, fewer, or the same?
Explain why. [At most 2 sentences.]
(c) Suppose a phrase appears exactly once in the training text. What probability does the model give the word that
follows it, and is that a reliable estimate? Explain. [At most 2 sentences.]

### Q2. What does this GPT-2 write? · short answer

`generate_with_transformer(model, prompt, seed)` continues a prompt by sampling each next token from the model's 50
most likely tokens. A student runs this code:

```python
from transformers import GPT2Config, GPT2LMHeadModel

config = GPT2Config(vocab_size=len(tokenizer), n_positions=128,
                    n_embd=256, n_layer=4, n_head=4)
model = GPT2LMHeadModel(config)

print(generate_with_transformer(model, "the old man walked into the", seed=BUID))
```

Which output did this code produce? Write its letter and explain your choice in one sentence.

- A. `the old man walked into the shop the attorney , " see , and being called his difficulties , which hung the hall to take it happens when it is the bannisters with a little boy scowled down little higher than he had bid farmer price`
- B. `the old man walked into the labeling lose - 1962closedertilityqv confusion puzzledjuries Matrix quotations NX specifying「 IVOLOG mL UPDATE irritation irritation allegationsizmodsCond({George iTunesPalestchanged Baghdad 163 niece pressed Scriptures os Underground revolver revolver tx`
- C. `the old man walked into the room and I saw no one. The doctor had a look of horror on his face, and said, [t]he man had been wounded so that I thought he had been seriously wounded when he`
- D. Nothing. The code raises an error, because this model cannot generate text yet.

### Q3. Testing on a different author · MCQ

A GPT-2 model is trained from scratch on the seven *Harry Potter* novels. It is then tested on *Percy Jackson and the
Lightning Thief* by Rick Riordan, a fantasy novel for young readers from the same period that was not in the training
data. Compared with its perplexity on the training text, its perplexity on *Percy Jackson* will most likely be:

- A. About the same, since both are fantasy novels for young readers
- B. Much higher, since the model memorized Rowling's exact word sequences, which Riordan doesn't repeat
- C. Lower, since a new text is easier to predict
- D. Exactly 1, since the language is similar

### Q4. Will it fit? · fill in the blanks

A model's weights need about **2 bytes per parameter** to load. Your app's host gives it 2.7 GB of memory. Fill in
the blanks.

- Llama 3.2 3B needs about ______ GB, so it ______ (fits / does not fit).
- Llama 3.2 1B needs about ______ GB, so it ______.
- Qwen2.5 0.5B needs about ______ GB, so it ______.
- Name one way, other than choosing a smaller model, to make Llama 3.2 3B fit: ______________.

### Q5. Medical bot assumes "he" · short answer

You are testing a medical chatbot that helps patients understand what their doctor told them. Testers never say
whether their doctor is a man or a woman, yet the bot almost always answers "He meant that…". Your team cannot
retrain or fine-tune the model. What causes this, and what steps would you take to fix it and to confirm it is
fixed? [At most 4 sentences.]

### Q6. The warranty answer · MCQ

A kitchen-appliance company's support chatbot answers customers with retrieval-augmented generation (RAG). When the
bot launched in January 2024, the team split every product manual into chunks, embedded them and stored them in a
vector database. A customer asks, "How long is the warranty on the X200 blender?" The bot answers "One year" and cites
the X200 manual's warranty section, which says "This product is covered by a one-year limited warranty." The product
team says the warranty is two years. You also find:

- Asked the same question 10 times, the bot gave the same answer every time.
- All 5 chunks the bot retrieved came from the X200 manual.

Which change would most likely fix the answer?

- A. Add "Answer only from the retrieved passages; if unsure, say you don't know" to the system instruction.
- B. Retrieve 20 chunks instead of 5, so the model sees more of the X200 manual.
- C. Switch to a larger, more capable model that is less likely to hallucinate.
- D. Rebuild the vector database from the current manuals, and update it whenever a manual changes.

### Q7. Same prompt, new answer · MCQ

Your customer-support app calls Gemini using the model name `gemini-flash-latest`, with temperature 0 and a fixed
seed. For three weeks the same test question has always returned the same answer. On Monday the answer changes,
though no one on your team changed the code or the prompt. What is the most likely cause?

- A. Temperature 0 only makes answers repeatable for a limited number of calls.
- B. Google pointed `gemini-flash-latest` to a newer model.
- C. The context window filled up from earlier calls.
- D. The seed expired and was replaced by a random one.
- E. None of these, because a model's version never changes once your code names it.

### Q8. Is chain of thought agentic? · true/false + one sentence

True or false: a chatbot that uses chain-of-thought reasoning before it answers is an example of agentic AI. Explain
in one sentence.

### Q9. What Gemini sees of a tool · true/false + one sentence

A notebook gives Gemini this Python function as a tool it may call: `ask_gemini(question, tools=[compound_interest])`.

```python
def compound_interest(principal: float, annual_rate_percent: float, years: float) -> float:
    """Return the final amount for money growing at a fixed annual interest rate.

    Args:
        principal: the starting amount of money.
        annual_rate_percent: the yearly interest rate as a percent (e.g. 6.46 means 6.46%).
        years: how many years the money grows.
    """
    return principal * (1 + annual_rate_percent / 100) ** years
```

True or false: to decide whether to call `compound_interest`, Gemini reads the Python code inside the function.
Justify your answer in one sentence.

### Q10. Is the long chat the problem? · MCQ, select all that apply

After a two-hour working session with Claude Code on your team's project, its answers feel less focused: it forgets
decisions you made early on and drifts off the task. You suspect the conversation has grown too long for its context
window. Which of the following would help you **check** that suspicion? **Select all that apply.**

- A. Start a new session, give it a short summary of the key decisions, ask the same question, and compare the answers.
- B. Ask Claude, in the same session, whether its context is too long.
- C. Raise the temperature and see whether the answers get better.
- D. Run `/context` to see how much of the context window is already used.
- E. Ask the same question three more times in the same session and compare.
- F. Turn on web search and see whether the answers become more focused.

### Q11. It passed the online question set · short answer

Your team built a Gemini-based assistant that answers questions about insurance claims, using RAG over your company's
policy documents. To test it, you downloaded a popular public collection of 1,000 insurance customer-service questions
with expert answers. The assistant answered 94% of them correctly. Your manager concludes it is ready to go live for
your company's customers. Give two reasons this conclusion is not justified, and say how you would test it instead.
[At most 4 sentences.]

### Q12. An agent wipes an inbox · short answer

In February 2026, a Meta AI safety researcher connected OpenClaw, an open-source agent that can run on top of any LLM,
to her real email account. She asked it to suggest which emails to archive or delete and to wait for her approval
before acting. It had worked well on a small test inbox. On her real inbox it started deleting hundreds of emails, and
her messages "Do not do that" and "STOP OPENCLAW" were ignored. A headline blamed "a rogue AI model." Would a better
model have been enough to prevent this? Explain what went wrong and what she should have done differently.
[At most 4 sentences.]

---

## Part 2 — Essays (52 points)

### Q13. Ship which version? · calculation (16 points)

Your company's travel assistant, built on Gemini, answers employees' policy questions. You test three versions on the
same question with the same model, changing one thing, five runs each. The question is "What is my meal allowance for
a two-day trip to Chicago?", and under company policy the right answer is $108. Prices: input $0.10 per 1M tokens,
output $0.40 per 1M tokens.

- **Version 1:** no access to the travel manual.
- **Version 2:** the model calls a search tool that returns the 10 most relevant sections of the travel manual.
- **Version 3:** the same search tool returns only the 2 most relevant sections.

| | Version 1 | Version 2 | Version 3 |
|---|---|---|---|
| Passed (answer = $108) | 1 / 5 | 5 / 5 | 4 / 5 |
| Tokens in / out per answer | 300 / 150 | 9,000 / 200 | 2,500 / 180 |
| Seconds per answer | 1.2 | 3.1 | 1.8 |

The assistant will handle 100,000 questions a month. Finance allows $50 a month for it, and the product team promised
answers within 2 seconds.

(a) Compute the cost per answer and per month for each version. [Show your calculation.]
(b) Which version would you ship? Explain what you gain and what you give up. [At most 3 sentences.]
(c) Version 1 gave the right answer in only 1 of 5 runs, while Versions 2 and 3 gave it in almost every run. Why?
[At most 2 sentences.]
(d) Finance points out that each wrong meal-allowance answer costs about $2 of staff time to correct the expense
claim. Treat Version 2's extra monthly token cost over Version 3 as the cost, and the correction costs it avoids as
the benefit. Compute the monthly **cost-benefit ratio** and **ROI** of choosing Version 2 over Version 3. Given this
result, would you now ship Version 2 or Version 3, and why?
[Show your calculation, then explain in at most 2 sentences.]

### Q14. Same setup, five different runs · short essay (10 points)

A company's IT help-desk assistant, built on Gemini, answers employees' support questions. To answer, the model
calls a search tool that returns the 10 most relevant sections of the IT support manual; those sections add about
9,000 tokens to the model's input each time the tool is called. You run it five times on the question "How do I
connect to the VPN from home?", changing nothing between runs, and log each run:

| Run | Passed | Tokens in | Tokens out | Seconds |
|---|---|---|---|---|
| 1 | ✓ | 9,000 | 200 | 3.0 |
| 2 | ✓ | 9,000 | 210 | 3.1 |
| 3 | ✗ | 9,000 | 950 | 9.8 |
| 4 | ✓ | 9,000 | 190 | 2.9 |
| 5 | ✓ | 18,100 | 220 | 5.4 |

(a) Run 3 failed. Looking at its tokens out and seconds, what most likely went wrong, and what would you do about it?
[At most 2 sentences.]
(b) Run 5 passed, but its tokens in are about double the other runs'. What most likely happened, and what would you do
about it? [At most 2 sentences.]
(c) Nothing changed between runs, yet runs 1, 2 and 4 wrote answers of different lengths. Why? [One sentence.]
(d) The average is 4.8 seconds per answer. Why is that a poor number to plan with, and what would you look at instead?
[At most 2 sentences.]

### Q15. Tracing a RAG chatbot · essay (12 points)

An HR chatbot is a Streamlit app on Streamlit Community Cloud. The employee handbook was split into chunks, embedded
with `gemini-embedding-001`, and stored in a vector database ahead of time. An employee types, in their web browser,
"How many vacation days do I get after three years?" List, in order, every exchange between the parts of the system
needed to answer, from the browser and back, with who contacts whom, the request and the response. Then say what
changes if the handbook is updated. [One sentence per exchange, at most 10 exchanges; then at most 2 sentences on the
update.]

### Q16. Reverse-engineering an apartment assistant · essay (14 points)

A classmate shows you this conversation with their Claude setup:

> **User:** Find me an apartment near BU.
>
> **Claude:** Happy to help. What's the most you can pay per month, how many bedrooms do you need, and when do you
> want to move in?
>
> **User:** 2 bedrooms, at most $3,200, moving in September.
>
> **Claude:** `search_listings(near="Boston University", bedrooms=2, max_rent=3200, move_in="2026-09")`
>
> | Rank | Address | Rent + fees per month | Bedrooms | Walk to campus | Note |
> |---|---|---|---|---|---|
> | 1 | 12 Egmont St | $3,050 ($2,950 + $100 fees) | 2 | 14 min | Laundry in unit |
> | 2 | 88 Pleasant St | $3,175 ($3,100 + $75 fees) | 2 | 22 min | Heat included |
>
> **Not checked:** 401 Park Dr (call for price), 9 Ivy St (no photos)
>
> My pick: 12 Egmont St, because it is cheapest and closest.
>
> **User:** Great, message the landlord of the first one and ask for a viewing.
>
> **Claude:** I can't contact landlords or agents. Here is the listing link so you can reach out yourself.

Explain what must have been set up to produce this behavior. Address each of the following:

(a) What did the model see besides the user's two messages? Where did the follow-up questions, the table format,
"Not checked" and "My pick" come from? [At most 3 sentences.]
(b) What tools or extensions does it use, and for what? Is any part of the table likely to be unreliable?
[At most 3 sentences.]
(c) Is this RAG? Point to what in the conversation supports your answer. [At most 2 sentences.]
(d) Why did it refuse to contact the landlord, and is that refusal reliable? [At most 2 sentences.]

---
