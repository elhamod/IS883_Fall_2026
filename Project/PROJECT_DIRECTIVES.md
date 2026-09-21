# IS883 — Term Project Directives

**Fall 2026 · Prof. Mohannad Elhamod · 45% of the course grade**

> This document is the single source of truth for the term project. Treat it as both a roadmap and the grading rubric. Where it conflicts with an announcement on Blackboard, Blackboard is correct.

---

## 1. At a glance

| When | What | Graded? |
| --- | --- | --- |
| **Mon Sep 21** (Session 2) | Teams formed by end of day | — |
| **Fri Sep 25, 11:59 PM** | **Team registered on Blackboard**, with a **primary idea and a backup idea** (§4.1) | Ungraded — **late penalty applies (§10)** |
| **\~Tue Sep 29** | **Idea verdict posted on Piazza and Blackboard** — go / shrink it / switch to your backup | — |
| **Mon Oct 5** (Session 4) | **Proposal due** (1 page, PDF, one per team) — includes your **repo link** (§4.2) | **Graded — 10% of the project grade (§8.1)** · late penalty applies (§10) |
| **By Tue Oct 13** (Session 5) | Written feedback returned on every proposal | — |
| **Mon Oct 19** (Session 6) | **Presentation-slot poll opens on Piazza** (§7) | — |
| **Thu Oct 22, 11:59 PM** | **Workshop checkpoint due** — written into your repository's `README.md`, whether or not you attend the workshop. **Your success metric is fixed here** (§4.3, §5.5) | **Graded — 10% of the project grade (§8.1)** · late penalty applies (§10) |
| **Fri Oct 23** (Session 7) | **Project workshop**, 6:30 – 9:15 PM, HAR 419 — the instructor visits each team, working from its checkpoint | — |
| **Fri Oct 23, 11:59 PM** | **Poll closes** — no response means you are placed wherever there is room | — |
| **11:59 PM, night before your slot** | **Slides + recorded demo fallback due** — final; **cannot be changed after you present** | Not graded separately — graded as part of the presentation and live demo (§8.2, items 6 and 7) · late penalty applies (§10) |
| **Before you walk up to present** | **Repo tagged** `presentation` — that tag is the graded code (§6.4) | Graded (§8.2) |
| **Mon Nov 9 / Mon Nov 16** (Sessions 10, 11) | **Presentations** — 12 min talk + 5 min live demo + 8 min Q&A | Graded (§8.2) |
| **Mon Nov 30, 11:59 PM** | **Written report due** (Blackboard) | Graded (§8.2) |

There is **no weekly homework** in this course. The project takes its place, it is **45% of your grade**, and it is expected to progress steadily from late September. The Oct 23 workshop is the only dedicated build-support session in the term, and it is a checkpoint on work already in flight — it is not the point at which the work should begin.

> **Start early.** You have six weeks of building between the proposal and the first presentation. A team that starts building in November will demo something that does not run.

---

## 2. Teams

- **Teams are 3–4 students**, self-selected, formed by the end of the day on **Mon Sep 21** (Session 2). Enrollment this term gives **7 teams** — five of four and two of three.
- **Register on Blackboard by Fri Sep 25, 11:59 PM.** The registration form is also where your primary and backup ideas go (§4.1), so have the conversation before you register, not after.
- **Registration is not graded, but it is subject to the project late policy (§10):** a team that registers after the deadline loses **10% of its project grade per midnight, to a maximum of 30%** — the same rule that applies to the proposal. Register on time; it is the cheapest 30% you will ever protect.
- If you are **not on a registered team** by Sep 25, you will be placed on one. In that case the deduction applies to **your individual project grade**, not to the grade of the team that receives you — a team that registered on time is not penalized for absorbing a latecomer.
- **Every member owns the whole project.** Design, coding, evaluation, writing, and presenting are shared. You may be asked in Q&A to explain any part of the work, including parts you did not personally write.

---

## 3. Your project — you choose it

**There is no dataset pool and no assigned topic.** You pick what to build. Make sure the complexity of your idea is appropriate for the course's timeframe.

Your project must satisfy the syllabus definition — an application that **(1) uses LLMs** and **(2) targets a real-world application based on social or business demand** — plus the technical floor in §5.1 and the ground rules in §3.2.

### 3.1 What makes an idea worth building

Four tests. An idea that fails any of them is not ready to register.

**1 · Who is the user, and what do they do today instead?** Name a person or a role, not "users" or "businesses." Then say what that person does right now to get this done.

**2 · What could it get wrong, and how would you know?** If you cannot name a way your app fails, you have not thought about it hard enough to evaluate it — and evaluation is the heaviest item on the rubric (§8.2, 20 points). You should be able to describe, before you write a line of code, the input that may break it.

**3 · Could your one-sentence description be pasted onto somebody else's project?** *"An AI assistant for X"* is a category, not a project. A strong description names the user, the input, what happens to it, and what comes back.

**4 · Why does this need a language model**? Say which part of your problem genuinely needs one — and, just as important, which part does not. A great many problems that look like LLM problems are better served by a query, a filter, or a rule, and those are cheaper, faster, and do not hallucinate. You develop this into a cited argument in §5.3; at registration, one sentence is enough.

|  |  |
| --- | --- |
| ❌ | *"A chatbot that answers questions about BU."* No named user, no sources, no task — and the model already does this, badly, on its own. |
| ❌ | *"An AI agent that automates business workflows."* A category. No user, no input, no output, nothing to measure. |
| ❌ | *"We fine-tune a model on our data."* Not taught in this course, not available on a free tier, and almost never the right answer to the problem you actually have. Prompting, tools and retrieval are. |
| ✅ | *"A Streamlit tool where a student-club treasurer pastes a semester of receipts; the app extracts each one into a structured row, checks it against the club funding rules we loaded as sources, flags the ones that violate a rule with a citation to that rule, and produces the reimbursement summary — measured on 25 real receipts against the treasurer's own manual coding."* Named user, named input, named sources, an output someone acts on, and a number you can report. |

### 3.2 Ground rules

**Personal data — only with consent.** You may build on data about real, identifiable people, **provided those people have given informed consent for this use.** Informed means they know what your app does with their data, they agreed to *this* use rather than to something general, and they can ask you to remove it. **Keep the consent in writing** — a form, an email thread, a signed sheet, or even in-app — and describe it in your proposal (§4.2, slot 3) and in your report.

Where you do not have consent, use synthetic data you generate, public institutional data, or documents your team owns. These are usually faster than the consent route, so take the personal-data path only when your project genuinely needs it.

**No unlicensed scraping.** Every source your app reads must be one you are permitted to use: a public API, an open dataset, official documentation, or documents you own. Scraping a site whose terms forbid it is out of scope for this course. **Your proposal names every source and says why you are permitted to use it** (§4.2, slot 3).

**Free tiers only, with a usage cap.** The whole app must run on the free tiers this course uses — the Gemini API free tier, Streamlit Community Cloud, a HuggingFace read token. **No project may require a paid plan.** And because your app is publicly reachable and the whole class will open it, you must cap usage: a per-session request limit held in `st.session_state`, and API keys stored in the platform's secrets rather than in your repository. **A key committed to a public repository is a live security incident, not a style problem** — revoke it immediately and tell us.

**About apps that advise people.** An app whose main job is to advise a real end user about their health, money, legal position, or safety is **not prohibited** — but it carries one hard requirement: **a disclaimer the user actually sees.** Your app must state that its output is generated by a language model and may be wrong, and it is not professional medical, legal, or financial advice.

---

## 4. Three checkpoints

Your idea is checked twice before you commit six weeks to it, and your build is checked once on the way. **Stage 1 is ungraded; stage 2 — the proposal — and stage 3 — the workshop checkpoint — each carry 10% of your project grade (§8.1).** All three carry the late penalty (§10). The reason for checking the idea twice is simple: the proposal is due Oct 5, and a team that discovers on Oct 13 that its idea cannot work has lost a month. The Sep 25 check is cheap and fast, and it exists to catch that a fortnight earlier.

### 4.1 Stage 1 — registration and idea check, due Fri Sep 25, 11:59 PM

Submitted on Blackboard, one per team. **You submit two ideas, and you must be willing to build either one.**

```
IS883 Team Registration — Fall 2026
Team name:              Members (full names and BU emails):

1. PRIMARY IDEA
   Who the user is (a person or a role, not "users"):
   What that person does today instead:
   What the app does, in one sentence:
   Why this needs a language model rather than a query, a filter or a rule (one sentence):
   Which three capabilities from §5.1 you expect to use, and where each fires:
   What you think will be the hardest part:

2. BACKUP IDEA
   Same six lines.
```

**What the backup is for.** It exists so that if we tell you your primary idea will not work, we can point you straight at something else rather than open a conversation. Ideas fail for reasons nobody can see in September — the source turns out to be behind a login, the API is not free, the scope is twice what you thought. When that happens the expensive part is not the failure; it is the fortnight spent deciding what to do instead.

**The backup needs to be a project you would actually be willing to build** — *"we'd figure something out"* is not a backup, and neither is something you named to fill the box. It may be a narrower version of your primary idea or a different project entirely.

**What comes back, by \~Tue Sep 29, posted on both Piazza and Blackboard:** one of three verdicts per team.

| Verdict | What it means |
| --- | --- |
| **GO** | Build it. Any notes attached are refinements, not conditions. |
| **SHRINK** | The idea is sound and too big. You will be told which part to keep. Proceed with the smaller version. |
| **SWITCH** | The primary idea cannot work here — scope, sources, cost, or §3.2. Proceed with your backup, or post a revised primary before **Fri Oct 2**. |

### 4.2 Stage 2 — the proposal, due Mon Oct 5

**One page, PDF, one per team. Worth 10% of your project grade (§8.1).** Its purpose is to get you written feedback while your direction can still change. **The proposal does not ask you to commit to an implementation** — you may change how you build this, and even what you build, up to your workshop checkpoint (§4.3), as long as you say so in it.

> **It is graded on effort, not on correctness.** You cannot lose a point for an idea that later turns out to be wrong, for a method you end up abandoning, or for writing *"we do not yet know how we will do this."* That candour is what the proposal is for. What loses points is a page that shows nobody spent an hour on it. See §8.1 for the scale — there are only three outcomes.

Use this template:

```
IS883 Project Proposal — Fall 2026
Team name:              Members (full names):

0. TEAM INFRASTRUCTURE
   GitHub repository link (if private, add the instructor and TAs as collaborators):
   Project board link (GitHub Projects — §5.7):
   Streamlit app URL (a placeholder app that deploys and says "hello" is fine now):

1. THE USER AND THE TASK
   Who the user is:
   The task, in one sentence:
   What they do today instead, and what your app adds:
   Why this needs a language model rather than a query, a filter or a rule (§5.3):

2. WHAT THE APP DOES
   The user's input:
   What comes back to the user:

3. SOURCES AND DATA
   Every source the app reads, and why you are permitted to use it (§3.2):
   Does any of it concern real, identifiable people? If yes, explain:

4. HOW YOU WILL KNOW IT WORKS
   The one number you intend to report (you fix this in your workshop checkpoint, §4.3):
   Where your 20 test inputs will come from:

5. SCOPE
   What is in the version you demo on Nov 9 or Nov 16:
   What you will cut first if you are behind on Oct 23:

6. RISKS
   What could make this project fail, in your own assessment.

7. WHAT YOU WANT FROM US
   One specific question for the instructor.
```

**Slot 5 is the one people skip and the one that saves projects.** Deciding in October what you will drop in November is a decision you can make calmly. Deciding it on Nov 8 is not.

**Late proposals** are subject to the project late policy (§10).

### 4.3 Stage 3 — the workshop checkpoint, due Thu Oct 22, 11:59 PM

**Written into your repository's `README.md` — there is nothing to submit. Worth 10% of your project grade (§8.1). Due the night before the workshop, whether or not your team attends.**

**What the workshop is.** On Fri Oct 23 the instructor goes round the room and spends a few minutes with each team: where you are, what your plan is, and the technical problem in your way. A few minutes is enough only if your thinking is already written down and has already been read — **so the checkpoint is prepared before class, not at the workshop.**

**Where it goes.** Add a section headed `## Workshop checkpoint` to the `README.md` at the root of your team's repository and fill in the template below. If your repository is private, the instructor and the TAs must already be collaborators (§4.2). **What is graded is your README as of the last commit before the deadline.** The commit history shows when every line was written, so there is no need to tell us you have finished.

**If your team is not attending the workshop,** the deadline is the same. Say so in slot 0, and you will receive written feedback in a private Piazza note by **Mon Oct 26**.

**Your success metric is fixed here.** The commit timestamp is the record that you chose your metric before you started tuning against it (§5.5). **Do not rewrite the checkpoint afterwards** — if something changes, add a dated note below it and explain the change in your report. You are not expected to know how to measure your metric well yet.

**Your app must be deployed.** The Streamlit URL in slot 0 must load. It does not yet have to do anything — a placeholder that deploys is enough.

```
## Workshop checkpoint
Team name:              Members (full names):

0. LOGISTICS
   Attending the Oct 23 workshop? (yes / no):
   Project board link (§5.7):
   Streamlit app URL (must load; it does not yet have to do anything):

1. THE PROJECT, AS IT STANDS TODAY
   Update these from your proposal — do not copy them across if they have changed.
   Who the user is:
   The task, in one sentence:
   The user's input, and what comes back to the user:
   Every source the app reads (§3.2):

2. WHAT CHANGED SINCE THE PROPOSAL
   What you changed in what you build or how you build it, and why (write "none" if nothing):
   What the proposal feedback asked for, and what you did about it:

3. WHERE THE BUILD STANDS
   What a user can do on the deployed app today:
   For each §5.1 capability you plan to use: where it will fire, and whether it is working / in progress / not started:
   A first sketch of your architecture diagram (§5.2) — a photo of a whiteboard, committed and linked, is fine:

4. SUCCESS METRIC (§5.5)
   The one number that says whether your app is doing its job:
   Where your test inputs will come from:

5. PROOF OF CONCEPT — TWO TEST INPUTS
   For each: the input · the result you expect, written before you run anything ·
   if your app can already run it, what it returned.
   Input A — an ordinary input your app should handle:
   Input B — an input you expect it to get wrong:

6. THE PLAN TO YOUR PRESENTATION
   What is left to build, and who owns each piece (it should match your board):
   What you will cut first if you fall behind:

7. WHAT YOU NEED FROM US
   The one thing blocking you, or the question you want answered at your table:
```

---

## 5. What the project must contain

These are the **musts** — the floor, not the target. §8.2 does not score whether you ticked them off; it scores how well you understood the choices behind them and whether the thing you built actually works.

### 5.1 The technical floor — deployment plus three capabilities

**Every project must be (a) deployed and publicly reachable on Streamlit Community Cloud, and (b) built on at least three of the four capabilities below.**

| \# | Capability | What counts |
| --- | --- | --- |
| 1 | **Structured prompting** | A system instruction plus a deliberate prompt structure — roles, few-shot examples, task decomposition, or an explicit reasoning pattern — held in a **versioned** variable so that a change to it can be tested against the previous version. "We wrote a good prompt" is not this. |
| 2 | **Tool calling** | The model decides to call a function you wrote, and the result comes back into the conversation and changes the answer. At least one tool the model genuinely chooses to invoke. |
| 3 | **Retrieval over your own sources** | Documents you supply, embedded and retrieved by similarity, with the retrieved text going into the prompt. Pasting one PDF into the context window is not retrieval. |
| 4 | **Structured output** | The model returns a schema your code parses and acts on — and there is a handled path for when it does not parse. |

**"Built on" means non-decoratively: removing the capability would change what the app does.** A tool the model never calls, a retrieval index that never influences an answer, and a schema nothing downstream reads do not count. **You will be asked in Q&A to show where it fires**, so build it so that you can.

A conversational interface, memory across turns (`st.session_state`), and sensible generation parameters are expected of every app and are not among the four — they are the baseline, not a capability you get credit for choosing.

### 5.2 The architecture diagram

**One diagram, in the report and on a slide, showing how information moves through your app** from what the user types to what they see. It must make clear:

- what goes **in**, and what comes **out**;
- every **stage** in between — where the model is called, where your code runs, where a tool or a retrieval step sits;
- **where each of your three §5.1 capabilities fires**;
- what happens on the **failure path** — where an unparseable response or an API error goes.

Draw it however you like. What is being scored is whether the picture is true: a diagram that does not match your code is worse than no diagram, and Q&A will compare them. Drawing this diagram early on, and regularly maintaining it, helps you develop your app on a solid foundation.

### 5.3 Related work — and why this needs an LLM

**Cite two or three sources** — academic papers, industry write-ups, or the documentation of an existing product — that show how your problem is solved today. Say briefly what each one does well and where it falls short for your user.

Then answer the question the whole course turns on: **why does this need a language model at all?**

A large share of problems that look like LLM problems are better solved by a database query, a filter, a rule, or a spreadsheet — and those solutions are cheaper, faster, and do not hallucinate. If a keyword search or an `if` statement would do the job, a language model is the wrong tool and choosing it anyway is a design error, not an ambition. **A team that can say precisely which part of its problem needs a model, and which part does not, is demonstrating exactly what this course is for.**

This is roughly three-quarters of a page in the report (§6.1) and one line in the proposal (§4.2, slot 1).

### 5.4 Sources and the things that break in public

- **Name your sources and keep them in the repository** (or, where they are large or licensed, name exactly where they come from and how to fetch them). A grader must be able to see what your app is reading.
- **Handle the failure paths.** An empty input, an input outside your app's scope, a model response that does not parse, and an API error are all normal and all will occur while the class is using your app. What the user sees in each case is part of what is graded.
- **Develop against two rows, not two thousand.** If your app loops the model over a huge amount of data, develop against a small sample or a couple of toy examples, and widen only once the output parses. This is how you avoid burning your free-tier rate limit on a broken prompt at 4 PM on workshop day.

### 5.5 Evaluation — required, and the heaviest item on the rubric

The syllabus commits you to this, and §8.2 gives it 20 points. **You fix your success metric in your workshop checkpoint (§4.3), due Thu Oct 22, before you change anything, and you are held to it for the rest of the term.**

The final deliverable must contain all five of these:

1. **A success metric, fixed in your workshop checkpoint (§4.3).** One number that says whether your app is doing its job. If you change it afterwards, say so and say why — a changed metric is defensible; a quietly changed metric is not.
2. **A test set of at least 20 real inputs.** *Real* means inputs a real user would actually give, not twenty variations you wrote because they pass. Include the awkward ones: an empty input, an input outside your app's scope, an input you expect it to get wrong. **Record the expected result before you run anything** — deciding what "correct" was after seeing the output is not a test.
3. **At least one deterministic check.** Something a program decides, not a human eye and not another model: was the tool called with the right parameter, does the JSON parse, does the answer contain the required citation, is the number inside the valid range. At least one of your checks must be of this kind.
4. **One measured before-and-after number.** Pick one change you made — a prompt revision, adding retrieval, a different parameter — and report the metric before and after, on the same test set. This is the only evidence you have that any of your work improved anything.
5. **One failure the metric could not catch.** Every metric is blind to something. Name one real failure that your number scores as a pass, and say what you would measure to catch it. **Doing this well scores above reporting a higher number.**

> **A low number honestly measured beats a high number nobody can believe.** Establishing that your app does not work as well as you hoped — with the evidence, a diagnosis, and what it would take to fix — earns full marks on item 4 of the rubric. Quietly narrowing the test set until the number improves earns none.

This is a short section of the written report and **about two minutes of the presentation**.

### 5.6 Financial model and cost analysis

**Your app is free to run because you are on a free tier. That is a fact about your student account, not about your idea.** This section asks what your app would cost if it were real, and whether it would be worth it. The techniques come from Session 9; the numbers come from your own app.

Required in the report (§6.1), and **about a minute of the presentation** — one number, honestly derived, and the assumption it rests on.

1. **Measured cost per interaction.** Not an estimate: read the token counts your own app reports across your test set and price them at the model's published rate. Show the arithmetic.
2. **Projected running cost at a stated volume.** Pick a user count and a usage frequency you can defend — *"400 club treasurers, six sessions a semester, nine queries a session"* — and carry it through to a monthly or annual figure. Include anything else the real version would pay for: hosting, storage, a vector database, a paid API tier you would need above the free one.
3. **The value side, and a break-even.** What does the app save or earn — hours of somebody's time at a stated rate, errors avoided, revenue enabled? At what volume does the value exceed the cost? If your app has no plausible financial case and its value is social rather than commercial, **say that and make the social case explicitly** — that is a legitimate answer, but it has to be argued rather than skipped.
4. **Your assumptions, stated in a list.** Every number above rests on assumptions. Write them down. A model whose assumptions are hidden cannot be argued with, which is the same as not being useful.
5. **A sensitivity analysis.** Take the one assumption that most changes the answer, move it — halve it and double it — and show what happens to your conclusion. **If your break-even flips when a single assumption moves by a factor of two, that is the finding**, and reporting it scores above a confident single number.
6. **Build versus buy.** One paragraph: you are calling a hosted API. What would change if you ran open weights yourself — cost, latency, control, privacy, and who maintains it? Session 9 gives you the frame.

> **The honest version wins.** A model that concludes *"this cannot pay for itself below 5,000 users, and here is why"* scores full marks. A model that reaches a comfortable ROI by assuming a number nobody could defend scores near zero, and it is the assumptions we will ask about.

### 5.7 How you work — the board

Your syllabus commits this course to an **Agile** approach, and the project is where that happens. The evidence is a **project board** — GitHub Projects is free, integrated with your repository, and enough.

- **Create it before the proposal** and link it there (§4.2, slot 0).
- **Every task carries an owner, a start and end date, a status, and a priority.** A board of untouched cards named "build the app" is not a board.
- **It must show movement over the weeks**, not a single burst. Its history is the picture of how your team actually worked, and it is one of the three things we compare against your contribution table.
- **It is linked in your workshop checkpoint (§4.3)** and in the report (§6.1). Screenshot it in the appendix.

> The board is not busywork and it is not a separate deliverable to invent in November. It is how a four-person team avoids discovering in week five that two people built the same thing and nobody built the retrieval.

### 5.8 Interpretation and communication

- Report what the numbers **mean**, in plain English that anyone in the room can follow. In your career you will be explaining this to people who do not know what an embedding is.
- **Every figure, in the report or on a slide, must have** axis labels and a legend where applicable, and a **one-line caption saying what the reader should conclude from it**. A figure without a takeaway is decoration.
- Tell the **story of how the app got better** — what you tried, what failed, what you changed, what it bought you. A team that reports only the final version has left out the most interesting part, and the part that shows what you learned.

---

## 6. Deliverables

All submitted through Blackboard except the code, which is the repository itself.

### 6.1 Written report — due Mon Nov 30, 11:59 PM

- **A single PDF.** Times New Roman, 12 pt, 1-inch margins.
- **Maximum 10 pages** for the main body, **including every figure in it**, excluding the cover page and appendices. Be ruthless about which figures carry an argument; the rest belong in an appendix. Appendices have no page limit.
- One report per team.

**The report must be self-contained.** If a claim needs a figure or a number to be understood, that figure or number belongs in the report or its appendix. **We will not open your repository to find something the report left out** — anything missing is simply missing, and is marked as such.

**Write your audience as someone deciding whether to fund this.** They are intelligent, they are not specialists, and they have read nine other reports today. That framing decides almost every choice you will make about what to include.

**Tell a story, do not answer a checklist.** Each section should lead into the next. A report structured as a series of disconnected answers to the headings below is much harder to read than one that reads as an account of what you set out to do, what you found, and what you would do next — and it reads as a team that never talked to each other.

#### The template

Follow this structure. The page budgets are guidance, not rules, but they add up to just under the limit — which tells you how tight the limit is, and that the appendix is where anything secondary belongs.

| Section | \~Pages | What goes in it |
| --- | --- | --- |
| **Cover page** | — | Title · team number and members · date. Not counted. |
| **Executive summary** | 0.25 | The problem, what you built, and your headline result — in two paragraphs, for a reader who will read nothing else. Write it last. |
| **1 · Problem and motivation** | 0.75 | What the problem is, who has it, what they do today, and why it is worth solving. |
| **2 · Related work, and why an LLM** | 0.75 | §5.3 — two to three cited sources, and the argument that a model is the right tool here. |
| **3 · Solution design** | 2 | The architecture diagram (§5.2) and its walkthrough; which three capabilities from §5.1 you built and where each fires; the design decisions you would defend and the alternatives you rejected. |
| **4 · Implementation** | 1 | What you actually built — model choice, generation parameters, code structure, the technical problems you hit and how you resolved them. |
| **5 · Evaluation** | 2 | §5.5 — all five elements. Usually the section that earns or loses the report. |
| **6 · Financial model and cost analysis** | 1.5 | §5.6 — all six elements, with the arithmetic visible. |
| **7 · Response to feedback** | 0.5 | Required. See below. |
| **8 · Limitations, and what you would do next** | 0.5 | Required. See below. |
| **9 · Contribution** | 0.5 | Required. See below. |
| **Appendices** | no limit | Generative AI appendix (§9) · project board screenshot (§5.7) · secondary figures · full test set · references. |

#### The four required sections, in detail

- **Evaluation** — report section 5. All five elements of §5.5.
- **Response to feedback** — report section 7. What the class and the instructor said when you presented, what you changed in the application afterwards, and what you decided not to change and why. Point at the commits after your `presentation` tag (§6.4). *"We agreed and did not have time"* is an acceptable and honest answer; silence is not.
- **Limitations** — report section 8. What might be wrong, uncertain, or sensitive to a choice you made? What was inconclusive? What would you do with more time, and why that? A report with no limitations section reads as one whose authors did not look for any.
- **Contribution** — report section 9. A table, one row per member, listing the concrete technical tasks that person personally carried out (*"wrote the retrieval function and tested chunk sizes of 200 vs 500 tokens"*, *"built the 24-case test harness and the JSON-parse check"*). Plain English, no vagueness. **Writing slides, editing prose, and coordinating the team do not count as technical contribution** — those are expected of everyone. Each row must **name the specific files or sections** that person wrote, so the table can be checked against the code comments, the commit history, and the project board (§6.4, §5.7). Include a sentence on how work was divided and how you handled it when a plan changed.

### 6.2 Slides — due 11:59 PM, the night before your slot

One deck per team, submitted to the single `Project slides` assignment on Blackboard. There is **one** assignment for all teams, not one per day; **your own deadline is the night before your own slot**, and submission timestamps are checked against it. Submitting early is fine and encouraged.

**Name the file exactly:** `Team##_ProjectTitle.pptx` (or `.pdf`).

**Both your slides and your demo run from the instructor's computer.** You will not connect your own laptop. This is why the deadline is the night before, and it is why your app must be deployed at a URL rather than running on somebody's machine.

> **The slides you submit are the slides you present, and they are the slides that are graded. They cannot be changed afterwards.** You may not revise a deck after hearing another team's talk or seeing the questions it drew.

### 6.3 Recorded demo fallback — due with your slides

**Every team submits a 2-minute screen recording of the app working**, at the same deadline as the slides, in the same Blackboard assignment. It can be played **if the live demo fails**, so that the class still sees what you built.

Record it from the deployed URL. The recording has to make sense to a room that has just heard your talk. Rehearsing the recording is most of the work of rehearsing the demo, so this is less extra effort than it looks.

**The fallback does not erase a failed demo.** See §7 for how the demo is graded.

### 6.4 Code, and the `presentation` tag — tagged before you present

**Your team keeps a GitHub repository.** Streamlit Community Cloud deploys from one, so you will have it whether or not this document required it — and it is one of the three ways we see who wrote what.

- **Create the repository before the proposal** and put its link in the proposal (§4.2). Public or private is your choice — if private, add the instructor and the TAs as collaborators.
- **Every member commits their own work from their own GitHub account.** One person uploading the whole project at the end defeats the purpose, and a commit history showing a single author invites hard questions in Q&A.

**The** `presentation` **tag is the graded artifact.** Before you walk up to present, create a release in your repository:

> GitHub → **Releases** → *Draft a new release* → tag name `presentation` → *Publish release*. No command line needed.

- **That tag is the version of your project that is graded.** Everything at the tag counts; nothing committed after it can raise your presentation, demo, build-quality or evaluation score.
- **The repository stays open after the tag, and you are expected to keep working in it.** That is where you incorporate the feedback from your presentation, and it is what your report's *Response to feedback* section points at (§6.1). Commits after the tag are not graded as code — they are evidence that you responded.
- **Your deployed app must stay reachable until your grades are submitted.** Do not delete the app when you present.
- The app must **run from a cold start** — restart it, open it in a private window, and confirm before you present.
- Code organized and commented well enough that a classmate could follow it.

#### Attribution — three layers, and they must agree

1. **A comment at the top of every section you wrote**, naming you: `# --- Priya: retrieval, chunking, and the similarity threshold ---`
2. **Your own commits** in the team repository.
3. **The contribution table** in the report (§6.1).

> **Putting your name on a section is a claim you will be asked to defend.** If you are asked in Q&A about a block of code with your name on it and cannot explain what it does and why you did it that way, that is worse than not having claimed it — it is a statement about the work that is not true. Claim what you did; do not claim what you did not.

> **Resubmission:** if you resubmit any Blackboard item, re-upload **all** of that item's files — earlier submissions are discarded and only the final one is graded. The code is never resubmitted; we take the `presentation` tag.

---

## 7. Presentation and Q&A

**Format: 12 minutes talk + 5 minutes live demo + 8 minutes Q&A. 25 minutes per team.**

**The clock is enforced and the cost is stated in advance.** The talk is stopped at **13:00** and the demo at **6:00**. Every minute over costs **10% of your presentation and demo score**, and whatever you had not yet said does not get said. If your team is not ready when called, you go to the end of the session and lose the minutes you wasted from your own time. Rehearse with a timer, out loud, more than once.

**Every member speaks, and each person presents their own work** — not a section somebody else built. A team where one person narrates everything has told us something about how the work was divided.

### Slots

**There are 7 teams: 3 present on Mon Nov 9, and 4 on Mon Nov 16.** The rest of each session is used for course material.

**Slots are assigned from a ranked-preference poll on Piazza, not first-come.** The two presentation days are not equivalent: presenting on Nov 16 buys you a week of extra build time, and your code is frozen at your own slot (§6.4). A race to click would hand a real advantage to whoever refreshes fastest. Note that Nov 16 has one more slot than Nov 9, so the later day is not the scarcer one.

- **Mon Oct 19** (Session 6) — the poll goes up on Piazza. One response per team: agree internally first, then have one member post on the team's behalf.
- **Fri Oct 23, 11:59 PM** — the poll closes. **A team that does not respond is treated as indifferent** and is placed wherever there is room.
- Shortly after, the assignment is posted on Piazza. It maximizes the number of teams getting their first choice and is run by a script rather than by hand.

> **Extenuating circumstances.** If a religious observance, a documented accommodation, a medical situation, or an obligation you genuinely cannot move affects which day you can present, **contact the instructor on Piazza before the poll closes on Fri Oct 23** — not after slots are assigned. Conflicts raised before the deadline are accommodated wherever possible. Once slots are assigned they are final, so raise it early even if you are not certain yet.

### What goes in the 12 minutes

Twelve minutes is not enough to walk through your project, and it is not supposed to be. **Your report carries the detail; the talk carries the argument.** Budget roughly:

|  |  |
| --- | --- |
| **The problem** — who the user is, what they do today, why this is worth building | \~2.5 min |
| **What you built and why** — the architecture diagram (§5.2), and the two or three design decisions you would defend | \~3.5 min |
| **Does it work** — your metric, your number, your before-and-after, and the failure your metric misses (§5.5) | \~2 min |
| **What it would cost** — one number from your financial model, and the assumption it rests on (§5.6) | \~1 min |
| **What it means** — what someone could now do differently, and what you would not yet trust it with | \~2 min |
| *Slack* | \~1 min |

**One minute is all the financial model gets on stage.** Give the headline figure and the assumption that most moves it; the full model lives in the report, and we will ask about it in Q&A. A team that spends three minutes on a spreadsheet has spent three minutes not making its argument.

**Deliberately leave out** of the talk: your prompt-engineering history one iteration at a time, every parameter you tried, your file structure, and the code. Those belong in the report, and we will ask about them in Q&A. You may add extra slides after the end of your deck to reference during Q&A only.

**Explain the problem before the solution.** A talk that opens with architecture has lost the room.

**No jargon, no name-dropping, no fancy words you cannot unpack.** A technical term may be used only if you **define it clearly the first time** it appears. Naming a technique without saying what it does and why you chose it counts against you: *"we used RAG"* is not an explanation. A word you cannot explain plainly when asked costs you more than the simpler word would have.

### The 5-minute demo

- **Run from your deployed URL**, on the instructor's machine, in front of the class. Not localhost, not a video, not a rehearsed screenshot walkthrough.
- **Show the app doing its actual job**, on a real input, end to end. Not the settings page and not the login.
- **Show it handling something awkward** if you can spare thirty seconds — an out-of-scope question, an empty input. A team that shows its app declining gracefully looks better, not worse.
- Expect the class to open your app during or after the demo. That is why §3.2 requires a request cap.

**If the live demo fails**, your recorded fallback (§6.3) is played so the class still sees the app. **The recording does not undo the failure.** What is graded is the app as demonstrated, together with your read of what went wrong: a team that names the likely cause and says what it would check scores meaningfully above a team that says nothing. A team with no recording to fall back on has a missing deliverable under §10 as well as a failed demo.

### What Q&A is for

**You are expected to defend your work and to answer questions about its details.** This is the part of the assessment that establishes the work is yours. Questions may go to **any member** of the team, about **any part** of the project — including parts you did not personally write. *"That was someone else's section"* is not an answer.

Expect to be asked things like:

- Show me where the tool actually gets called on your diagram — now show me that line in the code.
- Why retrieval rather than putting the whole document in the prompt?
- Which part of this genuinely needs a model, and which part could have been a rule?
- Twenty test cases — who decided what the right answer was?
- What is the failure your metric cannot see?
- What does a user see when the model returns something your code cannot parse?
- Where does your API key live, and what happens if someone hammers your app?
- Your break-even is at 2,000 users. Where did that number come from, and what happens at 1,000?
- Which assumption in your cost model are you least confident about?
- Your board shows this task took three weeks. What happened?
- What would you tell someone who wanted to actually deploy this next month?

**What scores well:** a direct answer with the reasoning behind it. *"We chose that, and here's why"* is a good answer. So is *"we tried that, it didn't work, and here's what we think went wrong."* So is **"I don't know — here's how we'd find out"**, which scores better than a confident guess and much better than a bluff.

**What scores poorly:** an answer that repeats a slide instead of addressing the question; a technical term used without being able to unpack it; any claim you cannot trace back to something in your code; and **"I don't know" with nothing behind it**. The good version of not knowing comes with a next step; the poor version is a full stop.

### How Q&A runs

The **first question comes from your classmates**, not from the instructor. The instructor asks after that.

**If you are in the audience, you are part of this session.** Asking a presenting team a substantive question is exactly the kind of contribution the participation policy asks for, and these two sessions are where every team should be doing it. The other half of that expectation is the attention rule in the syllabus: if you are asked something and it is clear you were not following, it costs **10% of your participation grade**, capped at 20% across the term.

Q&A is not a cross-examination and it is not about typos. It is a professional conversation about a piece of work, which is what these conversations look like after you graduate.

---

## 8. Grading

Your project grade has three parts:

|  | Weight |
| --- | --- |
| **The proposal** (§4.2) — pass / partial / fail | **10%** |
| **The workshop checkpoint** (§4.3) — pass / partial / fail | **10%** |
| **The final deliverable** — the 100-point rubric in §8.2 | **80%** |

### 8.1 The proposal and the workshop checkpoint — 10% each

#### The proposal

**Three outcomes. Nothing in between, and no partial credit inside a slot.**

|  |  | What it means |
| --- | --- | --- |
| **Pass** | **10%** | Every slot in the template is answered with something specific to *your* project. Your sources are named. Your scope cut in slot 5 is a real one you would actually make. Your question in slot 7 is one a generic team could not have asked. This is the expected outcome — most teams that take an hour over it land here. |
| **Partial** | **5%** | Submitted, but thin: slots answered in a sentence that would fit any project, sources unnamed, no real scope cut, or a slot left effectively blank. |
| **Fail** | **0%** | Not submitted, or submitted with so little content that there is nothing to give feedback on. |

**This is not a quality judgement on your idea.** The proposal is due before you have seen tools, retrieval, or evaluation, and its whole purpose is to let you change direction cheaply. A proposal that says *"we are not sure this is feasible and here is why"* is a **Pass** — that is exactly the thinking the stage exists to surface. A proposal whose idea we tell you to change is still a **Pass** if the page shows you did the work.

**A late proposal is separately penalized under §10**, and lateness and quality are scored independently: a thin proposal submitted on time still scores 5%, and a strong proposal submitted three days late still scores 10% before the §10 deduction is applied.

#### The workshop checkpoint

**The same three outcomes, read from your README as of the last commit before the deadline.**

|  |  | What it means |
| --- | --- | --- |
| **Pass** | **10%** | Every slot in the template is answered with something specific to *your* project. The app URL loads. The metric in slot 4 is a number something could actually compute, not an aspiration. Both test inputs in slot 5 have their expected result written down. |
| **Partial** | **5%** | Written, but thin: slots answered in a sentence that would fit any project, an app URL that does not load, a metric such as *"user satisfaction"* that nothing could compute, or test inputs with no expected result. |
| **Fail** | **0%** | Never written, or written with so little content that there is nothing to discuss at your table. |

**How far the build has got is not scored.** An app that deploys and does nothing yet is a **Pass** if the page shows you did the thinking, and so is a checkpoint that says *"retrieval does not work yet, and here is what we have tried."* What is scored is whether you know where you stand and what you will measure. **A late checkpoint is separately penalized under §10**, independently of its outcome, exactly as for the proposal.

### 8.2 The final deliverable — 100 points, 80% of the project grade

This rubric scores two things: **whether you understood what you were doing**, and **whether the thing you built actually works**.

It does not score whether you produced a checklist of artifacts. The requirements in §5 are the **floor, not the target** — meeting all of them mechanically, with no evidence of understanding behind the choices, is an *Acceptable* project, not a good one.

### How each item is scored

Every item uses the same six levels, and they score **understanding and effort together** — what you worked out, and what you actually did about it.

**Volume is not on the scale at all.** More pages, more charts, more features, more methods: none of these move you up it. Effort here means work that went into getting something right, not work that produced more output.

Note the gap at the bottom: a genuine attempt that misses the point still earns 70% of the item, but **an item you simply did not do is a zero**.

| Level | % of item | What it means |
| --- | --- | --- |
| **Excellent** | 100% | **Done properly, and understood.** The work is complete and correct, and justified with reasoning that shows why the alternatives were worse. The understanding is visible without anyone having to ask for it. |
| **Good** | 92% | **Done properly, and understood when asked.** Complete and correct; the reasoning is sound but you have to be asked for it. Minor gaps. |
| **Acceptable** | 87% | **One side is thin.** Either the work was done and the thinking behind it is shallow, generic or borrowed; or the thinking is sound and the execution is visibly rushed at the edges. |
| **Weak** | 80% | **One side is largely missing.** Either real work whose reasoning is absent, wrong, or contradicted by what the code actually does; or a sound idea left substantially half-built. |
| **Minimal** | 70% | **Little of either.** Attempted, but thin enough that neither the effort nor the understanding comes through. |
| **None** | 0% | **Not attempted at all.** Nothing to grade. |

### The items

| \# | Item | Pts | The question we are actually asking |
| --- | --- | --- | --- |
| 1 | **Problem, scope, and the case for an LLM** | 10 | Is there a named user with a task worth doing, and does your app address it? Everyone chose their own project, so **the choice is part of the work**: an idea that survives the four tests in §3.1 scores above one that reads like a category. Two things are scored here alongside it — **scope**, because a project cut sensibly and finished beats an ambitious one that half-runs; and **§5.3's argument that this needs a model at all**, cited against how the problem is solved today. |
| 2 | **Design choices and architecture** | 12 | Why *these* capabilities (§5.1)? Why a tool rather than a longer prompt, why retrieval rather than a stuffed context window, why this model and these parameters? Your architecture diagram (§5.2) is read here, and **it is read against your code** — a diagram that does not match what you built costs more than no diagram. This item is about the **choice**; whether you then built it correctly is item 3. |
| 3 | **Build quality and correctness** | 12 | Item 2 asks whether you designed sensibly. **This asks whether you then built it correctly.** Do the capabilities actually fire rather than sit there decoratively? Are the failure paths handled — bad input, unparseable output, API error, cold start? Are keys in secrets and is usage capped (§3.2)? Does the code do what the report says it does? |
| 4 | **Evaluation — did you measure it, and do you believe your own number?** | 20 | All five elements of §5.5: a metric fixed in your workshop checkpoint, 20+ real test inputs with expected results recorded in advance, at least one deterministic check, one honest before-and-after, and one named failure. **This is the heaviest item, because an app nobody measured has not been shown to work.** A low number honestly established scores full marks; a high number from a test set curated after the fact scores near zero. |
| 5 | **Financial model and cost analysis** | 10 | All six elements of §5.6: a measured per-interaction cost from your own token counts, a projection at a defensible volume, a break-even or an explicit social case, your assumptions listed, a sensitivity analysis on the assumption that matters most, and the build-versus-buy paragraph. **The assumptions are what we will ask about.** A model that concludes the app cannot pay for itself, and shows why, scores above one that reaches a comfortable ROI on numbers nobody could defend. |
| 6 | **Live demo** | 5 | Did the app do its job, on a real input, in front of the room, from its deployed URL? A failure costs what it reveals — a team that diagnoses it out loud scores above a team that goes quiet. **The recorded fallback (§6.3) is graded here, not separately:** if the live demo fails, it is what the room sees. |
| 7 | **Interpretation and communication** | 12 | Do the talk and the report explain the *why*, not just the *what*, to someone who does not know what an embedding is? Did you prioritize the argument over the detail in the 12 minutes you had? Does the report read as a story rather than a checklist? Do the figures carry their finding honestly? |
| 8 | **Defense, ownership, and contribution** | 14 | In Q&A: can **any** member explain **any** part of the work? Honest uncertainty — *"we don't know, and here's how we'd find out"* — scores above a confident guess; a bluff scores below silence. Scored here too: whether the technical work was genuinely shared, judged across your contribution table, your commit history, and your project board (§5.7). **Significant imbalance is penalized at the individual level.** |
| 9 | **Deployment and reproducibility** | 5 | Is the app publicly reachable and does it survive a cold start? Does the `presentation` tag contain everything, and could a classmate run it? |

**Item 9 carries more weight than its 5 points suggest.** If your app is not reachable and the tagged repository does not run, **your evaluation cannot be verified** — item 4 is then capped at *Minimal* on top of whatever item 9 itself loses. Open your own app in a private window before you present.

Work beyond the course content is welcome, and it shows up where it belongs — in items 2, 4 and 7 — but it never compensates for an app that does not work or a number nobody can believe. **Complexity is not a credential.**

---

## 9. Generative AI

The full policy is in the syllabus. For this project specifically — and yes, the irony of an AI course restricting AI is noted; the reason is below.

**Generating text with Generative AI is not allowed.** Every word of your report and your slides must be written by you.

- **Prohibited: having a Generative AI tool write, draft, expand, rewrite, summarise, or "polish" any prose** for the report or the slides — including a paragraph you then edit, and including a bullet list you then turn into sentences. If the sentence started as the model's, it does not belong in your report.
- **Permitted: light grammatical correction** — spelling, punctuation, agreement, a clumsy clause straightened out. The kind of thing a spell-checker does. The thinking, the structure, the argument, and the wording must be yours.
- **Permitted: ideation and coding.** You may use Generative AI to think through approaches, to explain a concept back to you, to debug, and to help write code.
- **Permitted: spell-checkers.** A spell-checker (such as Word's built-in checker)  needs no disclosure.
- **Disclose every use — not only code.** Any use of Generative AI on the project — ideation, explaining a concept, debugging, code — goes in the **Generative AI appendix** of the report (§6.1), as the syllabus requires: the tool and version, how you used it, and links or screenshots of the exchange. **Code a model helped write is also labeled where it sits**, with a comment at the top of the block naming the tool.
- **You are fully responsible for everything you submit.** AI-generated errors and hallucinations are your errors.

> **Why this rule, in this course.** You are being graded on whether you understand what you built. A report written by a model reads fluently and tells us nothing about you, which is exactly the failure mode this course spends thirteen sessions teaching you to recognize in other people's systems. The instructor may ask you to explain any part of your work; **inability to account for your own submission is treated as evidence that the work is not yours**, and is handled under the Academic Conduct Code. That applies to the writing as much as to the code.

Any violation of the AI policy is treated as a serious honor code violation.

---

## 10. Late policy

**10% of the project grade for each midnight that passes after the deadline**, applied to every dated project item — team registration and the idea check, the proposal, the workshop checkpoint, the slides, the recorded fallback, and the report.

> **Early items — team registration with the two ideas, the proposal, and the workshop checkpoint — are capped at a 30% deduction.** The deduction stops growing there, but the item is still expected: one never submitted takes the full 30% *and* forfeits its feedback. **Late items — the slides, the recorded fallback, and the written report — are not capped.** They keep losing 10% of the project grade for every midnight, with no floor, so a deliverable ten days late costs the entire project grade.

**The proposal carries a grade (§8.1) *and* this capped late deduction, and the two are independent.** The grade asks whether you did the work; the deduction asks whether you did it on time. A strong proposal handed in three days late scores its full 10% and then takes the 30% deduction against your project grade — which is far more expensive than the 10% it earned. Hand it in on Oct 5.

**The workshop checkpoint works the same way**, and because it is not submitted, **the commit timestamp on your README decides whether it was on time.**

Each item's deduction is applied once, to your project grade. For the slides and the recording, "the deadline" means **11:59 PM the night before your own slot**, not the night before the first presentation session.

**The code is not subject to a late penalty because it is not submitted late — it is tagged (§6.4).** A team that has not created the `presentation` tag when it presents is graded on whatever the repository holds at the moment it presents, and further commits do not count.

Deviating from submission instructions — submitting a link instead of a file, or the wrong filename — may cost up to 10% of the item.

---

## 11. Where to ask

**Piazza is the only contact channel for this course.** Post project questions there so the whole class benefits; mark a post private if it concerns something specific to your team. Office hours are by appointment and are the right place for anything that needs a screen share — request one with at least three time windows, each at least two hours wide, and say what it is about.

**Ask early about anything in §3.2.** A question about whether a data source is permitted takes us two minutes in September and costs you a project in November.