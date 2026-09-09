# Boston University Questrom School of Business

# IS883 – Deploy Generative AI in Enterprise
### Fall 2026

---

## Course Administrative Details

- **Instructor:** [Mohannad Elhamod](https://www.linkedin.com/in/mohannadelhamod/) (Contact exclusively through [Piazza](https://piazza.com/class/msf7c46jyov4tm/))
- **Office hours:** **By appointment only** — request an appointment through Piazza (see the Office Hours policy below)
- **TAs:** TBD (Contact exclusively through [Piazza](https://piazza.com/class/msf7c46jyov4tm/)); TA office hours are also **by appointment only**, requested through Piazza
- **Class time and place:** Monday 2:30 – 5:15 PM / HAR 419
- **Term:** September 2 – December 10, 2026
- **First class meeting:** Monday, September 14, 2026
- **Last class meeting:** Monday, November 23, 2026 (in-class final exam)
- **Number of sessions:** 13 — 11 regular meetings plus 2 makeup sessions
- **Makeup sessions:** Two sessions meet on a **Friday**, both **6:30 – 9:15 PM in HAR 419** — the usual room, but an evening start rather than the regular 2:30 PM: **Fri Oct 23** (session 7, project workshop) and **Fri Nov 20** (session 12, exam review).

> The instructor reserves the right to update the syllabus at any time.

> **About the makeup sessions.** These sessions fall outside the regular meeting pattern because of the instructor's scheduling constraints, and they substitute for the meetings that would otherwise have taken place at the end of the term. They are **not graded for participation** and **carry no graded assessment of any kind**. Their sole purpose is to give you additional time to prepare and review for the assessments that are graded. Attendance is strongly encouraged but is not part of your grade.

### No-class dates

| Date | Reason |
| --- | --- |
| **Mon Nov 30** | **No meeting** — replaced by the Fri Nov 20 makeup session. The final project report is still due this day, submitted through Blackboard. |
| **Mon Dec 7** | **No meeting** — replaced by the Fri Oct 23 makeup session. There are no class meetings in December. |

---

## Course Description & Learning Goals

This course offers an in-depth look at Large Language Models (LLMs) such as Gemini and Claude, with an emphasis on cloud-based AI (Artificial Intelligence). Utilizing the Gemini API and Claude, students will gain hands-on experience, harnessing the power of LLMs to transform their ideas into AI solutions. Additionally, the course will delve into advanced areas like prompt engineering and will address the societal implications of these powerful models. The course will also allow students to explore concepts, such as agile development and financial modeling, in a project-based framework.

Upon completion of this course, you will have:

- Gained a comprehensive understanding of Large Language Models (LLMs), including their functionality, capabilities, and limitations
- Leveraged LLMs within a cloud-based framework to address business and societal needs
- Grasped the multifaceted implications of LLM usage, including ethics, security, trustworthiness, and cost considerations

### A note on expectations

This is a technical course taught to a business audience. The material stays grounded in how these systems actually work and where they fail — not in what they are marketed as doing. You will read model outputs critically, write Python, and deploy a working application. A STEM background is not required, but keeping up with the hands-on work is.

---

## Course Structure & Pedagogy

Each session pairs a concept with hands-on work, and the two are not separable: the notebooks are where the concepts become concrete.

The team project runs across the whole term in an Agile fashion. Class sessions are used both to introduce new material and, at one point in the term, to provide a full session of in-class build support.

---

## Course Materials and Logistics

This class won't require the purchase of official materials. Readings are instead a curated selection of materials — research papers, blog posts, or multimedia content including talks and podcasts — posted per session.

### Required readings

Assigned per session and **linked directly from the course schedule below** — click the link in the *Preparation & Deliverables* column for that session. Anything that cannot be linked (a PDF excerpt, a local file) is placed in that week's `Required/` folder in the course repository instead. Sessions marked *none* have no new required reading. **These must be reviewed before class**, as they are essential to a meaningful in-class discussion, which constitutes a significant portion of your final grade.

### Optional readings

Supplementary materials for going further are placed in each week's `Optional/` folder in the course repository. They are never assumed in class and are never assessed.

### Software and accounts

This course necessitates the use of a few digital services. For each of these, a free tier is available and sufficient for class and project activities. However, it is your sole responsibility to use these resources judiciously.

- A free [Claude account](https://claude.ai/). Create it before the **Mon Sep 14** first session; it is used in class at several points during the term.
- A free [Gemini API account](https://aistudio.google.com/) — this provides the API key you will call from code. Create it before the **Mon Sep 28** session. Further instructions on proper API usage are given in class.
- [Gemini Notebook](https://notebook.google.com/) — a hosted tool that answers questions only from sources you upload or link, rather than from the model's own memory. It is used in class to show a packaged retrieval system before you build the same mechanism yourself in code. It signs in with the **same free Google account** you already need for Colab and the Gemini API, so there is nothing extra to install and nothing to pay for; the free tier covers everything this course asks of it. Sign in once before the **Tue Oct 13** session. (Until July 2026 this product was called NotebookLM, and `notebooklm.google.com` still redirects to it.)
- You will also use [Streamlit Community Cloud](https://streamlit.io/cloud) to deploy Gen-AI driven applications with user-friendly interfaces.
- A free [HuggingFace account](https://huggingface.co/join) with a **read** token. HuggingFace is where open-weight models are published; you will download one onto a Colab GPU and call a much larger one through its API, in the same notebook, to see what each choice costs. A free account includes a small monthly inference credit, which is more than enough for this course. Create it before the **Mon Sep 28** session.
- [Ollama](https://ollama.com/download) — a free desktop application that runs an open-weight model entirely on your own laptop: no account, no API key, and no network connection once the model is downloaded. You will use it in class to watch a small model generate tokens on your own hardware and to compare a small model against a larger one. **Do all of the following before the Mon Sep 21 session:**
    1. Download and install Ollama from [ollama.com/download](https://ollama.com/download), choosing your operating system. Installing it does *not* by itself download a model.
    2. Open a **command line**. This is a window where you type commands instead of clicking: on **Windows** open *Command Prompt* or *PowerShell* (press the Windows key, type `cmd`, press Enter); on **macOS** open *Terminal* (press ⌘ + Space, type `Terminal`, press Enter); on **Linux** open your *Terminal* application.
    3. Type `ollama pull llama3.2:3b` and press Enter. This downloads the model — 2.0 GB, so **do it at home, not on classroom wifi.** Wait for it to finish.
    4. Check it worked: type `ollama run llama3.2:3b` and press Enter, ask it any question, then type `/bye` and press Enter to exit. If you get an answer, you are done and ready for class.

    A 3B model needs roughly 8 GB of free memory; if your machine cannot manage that, use `llama3.2:1b` in place of `llama3.2:3b` in steps 3 and 4, and say so in class. If you prefer a picture-by-picture walkthrough, [this Windows guide](https://www.gpu-mart.com/blog/how-to-install-and-use-ollama-webui-on-windows) covers the same install; the second half of it adds a browser chat interface that needs Docker Desktop, which this course does **not** require — the four steps above are all we use. An install guide will also be posted on Piazza after the first session.
- Slides, demos and assignments will generally be in the form of Google Colab notebooks and can be found through the course [GitHub link](https://github.com/elhamod/IS883_Fall_2026). The instructor reserves the right to update the content of this repo. You may "Watch" the repo to stay informed of all updates.
- [Terrier GPT](https://terriergpt.bu.edu/login) — free to you as a BU student. It is **not endorsed or required by this course** and carries no special status: like any other Generative AI tool, its use on graded work is limited to the cases where the instructions explicitly permit it, and it is strictly prohibited during the final exam. See the Use of AI policy below.
- **Examplify** — the exam application used for the in-class final exam. Installing it and confirming that it runs on your laptop is **your responsibility**; see the assessment details below.
- **Bring a laptop to every session.** Don't forget your power cord.

---

## Course Policies

### Contact Policy

**Piazza is the only channel for course communication.** All questions, discussion, and private messages to the instructor and the TAs go through Piazza. Messages sent by email or through Blackboard will most likely not receive attention.

Join the course Piazza site at **<https://piazza.com/class/msf7c46jyov4tm/>** **before the first class**, and do two things straight away:

1. **Use your formal name as it appears on Blackboard**, so your posts and participation can be matched to you.
2. **Turn on at least a daily email digest**, so you do not miss announcements. Click the **gear icon** in Piazza, choose **Account/Email Settings**, then under **Class & Email Settings** click **Edit Email Notifications** for this course, select **Daily Digest**, and click **Save**. ([step-by-step instructions](https://support.piazza.com/support/solutions/articles/48000574383-student-email-notification-settings))

When you post:

- **Address the post to the whole instructor team, not to one person.** In the *Post to* field, select all instructors rather than a single name — a post addressed to one person is the most common reason a question sits unanswered.
- **Choose the right post type:** a **Question** when you need an answer, a **Note** when you are sharing a resource or starting a discussion.
- **Post publicly by default.** Use a private post only for something personal — a grade, an accommodation, or a difficulty within your project team. Public questions get answered faster and help everyone.
- **Write a specific title**, say what you have already tried, and paste code and error messages as text rather than screenshots.
- **Search the existing posts first** — your question may already be answered.

New to Piazza? See [how to post a question](https://support.piazza.com/support/solutions/articles/48000574396-students-post-a-question), the [student help center](https://support.piazza.com/support/solutions/48000185443), or this [short video tutorial](https://www.youtube.com/watch?v=j7I_T3p-NPE).

### Office Hours

Office hours — for the instructor and for any teaching assistants — are held **by appointment only**; there is no standing weekly slot. To request a meeting, send a private Piazza message that lists **at least three possible time frames, each at least two hours wide** — for example, "Tue 1:00 - 3:00 PM, Wed 10:00 AM - 12:00 PM, Thu 3:00 - 5:00 PM." Broad windows are what make it possible to find an overlap on the first try; a request naming a single time or a narrow slot rarely lands. **State the purpose of the visit in the same message** — grade revision, project help, discussion of course content, and so on. That is what allows a request to be routed to the right person and prioritized against the others waiting.

**Requests that do not include three qualifying time frames will not be answered.** You will need to resubmit, which delays the meeting — often past the point where it would have been useful. A request that does not state its purpose may also be delayed while we work out who should take it. Plan ahead and send your request well before the deadline you need help with. Meetings are held in the instructor's office (HAR 546D) unless another arrangement is agreed in advance.

### Attendance Policy

Regular attendance and preparation are essential, as class sessions include hands-on activities and discussions that cannot be replicated outside of class. In accordance with Boston University policy and Massachusetts State Law, absences for religious observance are excused. The instructor should be notified in advance when possible.

Because in-class activities and discussion are central to this course and cannot be replicated afterward, your attendance and preparation are reflected in your participation grade (see the Course Evaluation & Expectations section below).

- **Two sessions meet on a Friday** — **Fri Oct 23** (session 7) and **Fri Nov 20** (session 12), both **6:30 – 9:15 PM in HAR 419**, in place of the dropped Mon Nov 30 and Mon Dec 7 meetings. The room is the usual one, but these sessions start in the evening rather than at 2:30 PM. Neither is graded for participation and neither carries a graded assessment; see *About the makeup sessions* above. Please put both on your calendar now and raise any conflict with the instructor in the first two weeks of the semester.
- There is no separate attendance rule and no fixed number of permitted absences. Attendance matters only through participation: participation cannot be earned in a session you are not present for, so students who miss a substantial number of sessions will find it difficult to score well on that component.
- Other assessments and in-class participation evaluation are not waived or postponed due to absence. The final exam is administered in class via Examplify on your own laptop. There are no makeup sittings as a matter of course; a **documented** medical or University-excused absence may be granted a makeup sitting at the instructor's discretion, arranged through Piazza **as early as possible** and normally before the exam. An undocumented absence from the exam receives a zero.

### Academic Accommodations for Students with Special Needs

In keeping with university policy, any student with a disability who needs or thinks they need academic accommodations must contact Disability & Access Services at 617-353-3658, or visit 25 Buick Street, Suite 300, to arrange a confidential appointment with a staff member. Accommodation letters must be delivered to your instructor in a timely fashion — within two weeks of the date on the letter, and not later than two weeks before any major examination. While reasonable requests will be accommodated when possible, please note that accommodations may still not be delivered absent an official letter of accommodation.

### Academic Conduct

Please refer to the [university's general academic integrity policy](https://www.bu.edu/provost/students/undergraduate/academic-integrity/) and [code of conduct](https://www.bu.edu/academics/policies/academic-conduct-code/). Unless specifically instructed to the contrary, these policies will be enforced, and the procedures of BU's Academic Conduct Code are followed wherever there is clear evidence of a violation.

- **Assessments.** Cheating includes any copying or sharing of answers, or any attempt by a student to alter their own or another student's performance on an assessment in violation of that assessment's stated or commonly understood ground rules. Use of electronic devices or supplemental material that is not explicitly allowed is also a violation.
- **Coursework and projects.** Copying another student's or team's files, data, or project — including from a previous year — and representing the work as your own is a violation, as is copying the exact wording of another write-up. Where there is reason to believe that part of a submission was copied, it will receive a zero pending review.
- **Course materials.** Posting course material of any kind — assessments, slides, notebooks, or completed projects — to the web is expressly prohibited. This includes crowd-sourced platforms such as Course Hero and SlideShare.
- **Citations and references.** For all submissions, citations and references to any articles, repositories, or other materials used are required. Omission will lead to losing points, and non-compliance constitutes a violation of the honor code that will result in appropriate disciplinary action.

### Use of AI

**Where Generative AI is permitted in this course.** Generative AI is the key topic of this course. Even so, its use on any graded component is strictly limited to cases where it is explicitly permitted in the instructions. Some assessments are designed to evaluate your ability to apply GenAI tools effectively; others aim to assess your independent reasoning, comprehension, and technical skills without GenAI assistance. The final exam is closed-book and administered in a locked-down Examplify session with no internet access, so no AI tools of any kind can be or are permitted during it; Colab's AI features must be turned off during the exam. [Terrier GPT](https://terriergpt.bu.edu/login) is free to you as a BU student and is one option among others; it is not endorsed or required, and using it carries exactly the same disclosure and defence obligations as any other tool. You are responsible for adhering to the expectations set for each assessment.

**Requirements for use.** Wherever an assessment explicitly allows Generative AI (e.g., ChatGPT, Gemini, Claude, GitHub Copilot), all of the guidelines below must be followed.

**Attribution & transparency:**

- Clearly identify all AI-generated content, even if it was only used for idea generation or editing.
- In-text citations or footnotes should reference the AI tool and the prompt used.

**Required appendix.** Each submission using AI must include a short appendix that contains:

- The specific tools and versions used (e.g., ChatGPT-4.1)
- A brief description of how the AI was used (e.g., brainstorming, coding assistance, debugging)
- The full exchange with the AI tool in the form of weblinks or screenshots (relevant parts may be highlighted)

**Accuracy & responsibility.** AI tools frequently generate incorrect or fabricated facts, citations, or code. You are fully responsible for verifying the accuracy of all AI-assisted content. Any errors or hallucinations will be treated as your own.

Using Generative AI tools for plain English writing is strictly prohibited. All written work, such as reports, must be created in your own words.

Any submission that violates these requirements may be treated as a violation of academic integrity and will be handled in accordance with the Academic Conduct Code. The instructor reserves the right to call you to office hours to discuss your submitted work and determine whether you understand it or simply copy-pasted it from a Gen AI tool. AI should deepen your understanding, not replace it. You are expected to remain intellectually engaged and responsible for the content you submit.

> **Note:** The type of tool does not change these requirements. "Generative AI" includes not only standalone tools like ChatGPT, Gemini, Gemini Notebook, and Claude, but also GenAI tools embedded within coding platforms (e.g., GitHub Copilot, Google Colab, or VS Code extensions).

To help clarify expectations, here are some examples:

- ✅ **Acceptable:** Using an AI assistant to help you understand the effect of the "context window" and citing it in your submission.
- ❌ **Unacceptable:** Using AI tools to generate a paragraph about "context window" without understanding or citing the assistance.

**Collaboration (PROJECT ONLY).** The goal of this course—and of your education more broadly—is to prepare you for real-world success. Given the importance of teamwork and communication in business and analytics roles, student discussions are encouraged. Sharing ideas, debating approaches, and supporting each other's learning is welcome as long as it is done transparently and with intellectual engagement. You may discuss general concepts, methods, and high-level strategies, but you may not share or view each other's code, written answers, or specific solution details unless working on a designated group assignment or project. You are still expected to fully understand, explain, and take ownership of any work submitted under your name. You must be able to discuss and defend your code, analysis, and conclusions when asked. Any help or collaboration—whether from classmates, tutors, or AI tools—must be clearly cited in your submission. This includes conversations that influenced your thinking, even if you did not directly use someone else's code or answers. Failure to adhere to these guidelines may constitute a violation of the Academic Conduct Code.

- ✅ **Acceptable:** Discussing the strengths and weaknesses of different Gen AI models with a classmate.
- ❌ **Unacceptable:** Copying or closely mimicking another student's code, even with small modifications.

### Professional Conduct Policy

- **Bring your laptop:** You will need it for in-class coding in nearly every session. Don't forget your power cord.
- **Laptops open for coding only:** Screens are open during hands-on coding activities and closed during discussion, demos, and lectures. For notetaking outside coding activities, please use a paper notebook or a tablet with a pen (no keyboards).
- Cellphones are prohibited unless specifically allowed by the instructor for certain in-class activities.
- Activities unrelated to class — social media, news sites, video, gaming, email, messaging — are not permitted at any time.
- **Place your name tent:** This helps your instructor learn your names, and it is needed so that your participation can be recorded. Please use your formal name as shown on Blackboard.
- **Punctuality:** Students are expected to arrive on time.
- **Pay attention to whoever is speaking:** whether that is the instructor or a fellow student. See *Class participation* below for what happens when it is clear you were not.
- Food is not allowed. Drinks are OK if consumed in an undistracting way. A 15-minute break is provided midway through the class.
- **Violations:** The first violation of any of these policies will incur a warning. Subsequent violations will warrant losing 1 point of the final course grade per citation.

### Diversity & Inclusion

This course is developed with attention to how identity and culture shape its content. Throughout the term, the emphasis is on knowing where your data came from, and how and why it was collected, so that potential sources of bias can be recognized. Perspectives related to the course content are invited. If there are topics that would benefit from additional social context or a differing perspective, let your instructor know, and resources and opportunities will be sought to bring a wider range of perspectives into the classroom.

### Sexual Misconduct / Title IX

The Questrom School of Business is committed to fostering a safe learning environment and preventing sexual misconduct. All forms of sexual misconduct — including rape, acquaintance rape, sexual assault, domestic and dating violence, stalking, and sexual harassment — violate BU policy, whether they happen on or off campus. Title IX of the Education Amendments of 1972 prohibits sex-based discrimination in federally funded education programs. If you or someone you know has been harassed or assaulted, resources are available at [http://www.bu.edu/safety/sexual-misconduct/](http://www.bu.edu/safety/sexual-misconduct/).

---

## Course Evaluation & Expectations

For details on Questrom's program-wide guidelines for grading, please refer to the [provided link](https://www.bu.edu/academics/questrom/policies/grades-and-course-credits/). Questions about a grade received on a particular assessment must be raised within one week of receiving it; otherwise, the grade may not be revised. If you have particular grade-related considerations that you think are important, please raise these with your instructor as early as possible (during the first half of the semester at the latest), so that your instructor can help you approach the course in a way that will help you achieve your best possible performance.

The relative weight of assessments in your course grade is as follows:

| Component | Weight |
| --- | --- |
| Class participation | 25% |
| Team project | 45% |
| In-class final exam | 30% |
| **Total** | **100%** |

**Class participation (25%).** The instructor will regularly engage you in discussion and seek your insights and perspectives dialectically. As such, you are expected to maintain consistent attendance and active participation, including familiarity with the required readings and preparation questions.

**Cold-calling is not how this course is run.** Participation is something you offer, not something extracted from you, and the plan is never to put you on the spot. The one situation in which the instructor will call on a student directly is when that student is plainly not following the class — distracted, disruptive, or in breach of the laptop and phone rules in the Professional Conduct Policy. In exchange, the bar is explicit and it is small:

| Substantive contributions over the term | Participation score |
| --- | --- |
| 3 or more | 100% |
| 2 | 90% |
| 1 | 80% |
| 0 | 70% |

**A contribution counts when it moves the discussion** — a question that identifies a real difficulty, an answer that engages with the substance, a challenge to a claim made in class or by another team, a point raised during hands-on work, or a substantive question put to a presenting team. Speaking in order to be recorded as having spoken does not count, and quality is what decides whether something is counted at all rather than being scored separately.

**Attention is expected of the audience, not only of the speaker.** When the instructor or a fellow student is presenting or leading a discussion, you are expected to be following it. If the instructor asks you a question and it is clear that you were not paying attention, that costs **10 percentage points of your participation grade** — for example, a student who had earned 100% drops to 90%. It applies per incident and **is capped at 20% deduction**, so it can lower a participation grade but can never sink it on its own. This matters most during the two presentation sessions, where the audience is being asked to carry half the Q&A.

Three contributions across ten graded sessions is a low bar, and the two presentation sessions alone give every team an opportunity to question another. If you are at zero by mid-semester you will be told. **A tentative participation grade will be shared mid-semester as a form of feedback**, so you have time to adjust. The two Friday makeup sessions are not graded for participation; see *About the makeup sessions* above. Name tents are required in every session so that your contributions can be recorded.

**Team project (45%).** Early in the semester, students will be grouped into self-selected teams of 3–4 students. Each group will propose a project that (1) uses LLMs and (2) targets a real-world application based on social or business demand. Once project ideas are approved, teams adopt an Agile approach and develop their projects across the term, with ungraded in-class workshop time available for support along the way.

**The project grade has two parts: the proposal is worth 10%, and the final deliverable 90%.** The proposal, due early in the term, is scored pass / partial / fail on **whether you did the work — not on whether your idea turns out to be right**: a proposal whose direction we ask you to change still earns full marks if the page shows you did the thinking.

The final deliverable is assessed at the end of the term: teams present their completed work to the class across **Mon Nov 9 and Mon Nov 16**, address questions, and gather feedback, then incorporate that feedback into the application and submit a final report. A team's code is frozen at the moment it presents — it tags its repository — and the presentation is graded as given; the repository then stays open for the changes the team makes in response, which the report describes. **The written report is due Monday, November 30**, two weeks after the last presentation session. There is no class meeting that day; the report is submitted through Blackboard.

**Evaluation is a required part of the final deliverable.** Each team writes down a success metric during the Oct 23 workshop and then reports against it: a test set of at least 20 real inputs, at least one deterministic check, one measured before-and-after number for a change the team made, and one failure the metric could not catch. This is a short section of the written report and about a minute of the presentation.

**`Project/PROJECT_DIRECTIVES.md` in the course repository is the single source of truth for the project** — requirements, both templates, deliverables, the presentation format, and the full 100-point rubric. Each student is expected to fully grasp, discuss, defend, and take ownership of the entire project. All team members must therefore actively engage in various aspects of their projects, including research, coding, documentation, and presentation. Significant imbalances in the distribution of responsibilities or the type of work undertaken by team members will result in penalties.

**In-class final exam (30%).** A single, closed-book exam administered **in class** in the last session, **Monday, November 23**, covering the technical concepts from the lectures and notebooks. **The exam is delivered via Examplify on your own laptop.** Examplify locks the machine down for the duration: there is no internet access, no interpreter or notebook, and no access to your own files, so **you will not run code during the exam** — questions ask you to read, reason about, and where relevant hand-write code. **No electronic device of any kind** other than the laptop running Examplify may be used or accessible during the exam — no second laptop, tablet, phone, or smartwatch. (This restriction applies to the exam only. During hands-on class activities your laptop is expected, and other devices may be used whenever the instructor explicitly authorizes them.) It is designed to assess your independent understanding, so Generative AI tools — including Terrier GPT — are not permitted. A full review session is held three days earlier, on **Friday, November 20** (makeup session 12).

**It is your responsibility to install Examplify and verify that it runs on your laptop well before the exam.** Questrom IT is the support channel for installation problems and can provide a loaner laptop if needed. The instructor does not run a setup check and is not responsible for troubleshooting your machine; a device that fails on exam day is not grounds for a makeup sitting.

There are no makeup sittings as a matter of course. A **documented** medical or University-excused absence may be granted a makeup sitting at the instructor's discretion; contact the instructor through Piazza as early as possible, and normally before the exam. An undocumented absence from the exam receives a zero.

**Late submission.** 10% is deducted for each midnight that passes following the deadline indicated in the course schedule, with one distinction between deliverables:

- **The early deliverables** — team formation and the project proposal — are capped at a **30%** deduction and are **still expected**. The deduction stops growing at 30%; a deliverable that is never submitted at all receives the full deduction and forfeits its feedback. In both cases the deduction is applied to your final project grade. Note that **the proposal also carries 10% of the project grade in its own right** (see *Team project* above), and the two are independent: the grade asks whether you did the work, this deduction asks whether you did it on time.
- **The final written project report** carries **no cap**. The deduction keeps growing for each midnight that passes, so a report ten days late costs you the entire project grade.

Deviating from submission instructions (e.g., submitting a link instead of uploading a file) may lead to a penalty of up to 10% of the assessment's grade.

---

## Other Logistics

**Blackboard usage.** Blackboard is where all deliverables, their deadlines, and your grades are posted. Course materials — required and optional preparation, notebooks, and demos — live in the course repository, not on Blackboard. It is essential that you pay close attention to Piazza announcements, which contain critical information. While a weekly announcement is generally sent as a reminder, it remains your responsibility to set up your alerts appropriately for any updates in the schedule, assignments, or reading materials.

---

## Course Schedule

> Note that while the following table provides a holistic overview of the course's schedule, it is only meant to give general guidance. Exact dates and deliverables are confirmed on Blackboard; each session's required reading is linked directly in the last column. Whenever there is a conflict between the syllabus and Blackboard on dates or deliverables, Blackboard is correct.

| # | Date | Learning Objective | Topics & Concepts | Preparation & Deliverables (BEFORE class unless stated otherwise) |
| --- | --- | --- | --- | --- |
| 1 | Mon Sep 14 | **Machine learning for language modeling.** Understand what a language model is and how a model trained on text can generate and complete it, and see the over/under-fitting trade-off in a language setting. | N-gram models; train/test split; sampling vs. lookup; stochasticity and seeding; perplexity; effect of context size *n* (nltk) | **Required:** create a free [Claude account](https://claude.ai/) · **Required reading:** [What does it mean for computers to understand language? \| LM1 (vcubingx video, ~12 min)](https://www.youtube.com/watch?v=1il-s4mgNdI) · [Meet Moltbook, the Social Media Site Where AI Agents Run Wild (Built In, ~8 min read)](https://builtin.com/articles/what-is-moltbook-openclaw) |
| 2 | Mon Sep 21 | **From n-grams to transformers.** Explain how transformers differ from n-grams and why the volume of training data — not the architecture — separates a toy model from a useful one, and compare models fairly. | Tokenization; embeddings; training from scratch vs. pretrained; context window; per-word perplexity; HuggingFace pipelines (translation, sentiment) | Team formations in class · **Team registration, with your primary and backup project ideas, due Fri Sep 25, 11:59 PM on Blackboard** (after this session; see `Project/PROJECT_DIRECTIVES.md` §4.1) · **Required:** install [Ollama](https://ollama.com/download), then type `ollama pull llama3.2:3b` at a command line (Command Prompt/PowerShell on Windows, Terminal on macOS or Linux) — 2.0 GB, download at home, not on classroom wifi; [step-by-step instructions](https://www.gpu-mart.com/blog/how-to-install-and-use-ollama-webui-on-windows) · **Required reading:** none new — rewatch [What does it mean for computers to understand language? \| LM1 (vcubingx video, ~12 min)](https://www.youtube.com/watch?v=1il-s4mgNdI) from Session 1; we pick its thread back up at the top of this session |
| 3 | Mon Sep 28 | **Deploying an LLM web app.** Build and deploy a simple web app that calls a hosted LLM and maintains conversation state, and weigh hosting a model against renting one. | google-genai SDK calls; API keys and secrets; generation parameters (temperature, max tokens, seed, stop); Streamlit UI; `st.session_state` memory; GitHub deployment to Streamlit Community Cloud; open weights vs. hosted API (running Llama 3.2 3B on a Colab GPU vs. calling Llama 4 Scout through the HuggingFace API); chat templates; per-token cost estimation | **Required:** create a [Gemini API key](https://aistudio.google.com/), a [Streamlit Community Cloud account](https://streamlit.io/cloud), and a [HuggingFace read token](https://huggingface.co/join) · **Required reading:** none — the accounts above are this session's preparation |
| 4 | Mon Oct 5 | **Prompting, reasoning, and hallucinations.** Write effective prompts, apply reasoning patterns, and recognize and limit hallucinations. | Prompt and system-instruction structure; few-shot prompting; Chain-of-Thought; task decomposition; structured output; causes and mitigation of hallucinations ("AI slop") | Project proposal · **Required:** [The Problem with A.I. Slop! (Computerphile video, ~18 min)](https://www.youtube.com/watch?v=vrTrOCQZoQE) |
| 5 | Tue Oct 13 *(substitute Monday schedule)* | **Giving LLMs tools and knowledge.** Give an LLM actions (tools) and external knowledge (retrieval) in code, and explain what a packaged retrieval product is doing on your behalf. | Automatic function calling; ReAct (Reasoning + Acting) — the reason/act/observe loop, written in code; embeddings; cosine-similarity retrieval (NumPy); RAG pipeline (optional Chroma); Gemini Notebook as a packaged RAG system — importing sources found online, answers grounded in those sources with citations, and how retrieval fails | Sign in to [Gemini Notebook](https://notebook.google.com/) with your Google account · **Required:** [AI Agents vs Workflows — What Actually Makes an Agent (DataMListic video, ~4 min)](https://www.youtube.com/watch?v=3jIUB1Fc0Yc) |
| 6 | Mon Oct 19 | **The Claude ecosystem and MCP.** Use assistant tools (chat, Projects, Cowork), skills, and automation to augment workflows, and understand how tools and data connect through a standard protocol. | Claude chat/Projects/Cowork; skills; automation; Model Context Protocol (MCP) and connectors (concept and demo) | **Required:** none — this session is built around a live demo |
| 7 | **Fri Oct 23**, 6:30 – 9:15 PM, HAR 419 *(makeup session)* | **Project workshop.** Build and debug the team prototype in class with instructor and TA support, and review scope and architecture. | Applying the course stack to the team project (API calls, prompting, tools and retrieval, Streamlit deployment); GitHub versioning; scoping and debugging; incorporating feedback | **Required:** [LLMs in Production §10.4, “Lessons learned and next steps” (Manning liveBook, ~8 min)](https://livebook.manning.com/book/llms-in-production/chapter-10) — free to read in the browser with a Manning account · *Makeup session — not graded for participation; no graded assessment* |
| 8 | Mon Oct 26 | **Trustworthiness, safety, and evaluation.** Explain why LLMs are unreliable at exact computation and how alignment training shapes their behavior, reason about safety, and measure whether a deployed system is actually working. | Tokenization limits on arithmetic; tool use as a fix; instruction fine-tuning; RLHF / preference tuning; safety failure modes; evaluating a deployed system: fixed prompt test sets; deterministic (programmatic) checks; overlap metrics (ROUGE, BLEU) and their limits; embedding similarity; LLM-as-judge and its biases; A/B on prompt changes; re-testing when a provider upgrades a model; the limits of public benchmarks | **Required:** [AI Fails at 96% of Jobs (ColdFusion video, ~15 min — stop at the sponsor read)](https://www.youtube.com/watch?v=z3kaLM8Oj4o) |
| 9 | Mon Nov 2 | **IP, cost, and bias.** Assess the legal, environmental, financial, and fairness implications of deploying generative AI in a business. | Training-data IP and copyright; energy and compute footprint; token-based cost modeling; build-vs-buy and model-size trade-offs; sources of bias (data, objective); probing and measuring bias; mitigation approaches | **Required:** [AI companies buying books to scan and destroy (CBS News video, ~5 min)](https://www.youtube.com/watch?v=7u1FZzhp5aw) |
| 10 | Mon Nov 9 | **Final presentations (1 of 2).** Deliver a complete project and defend design decisions in response to questions. | Presentation; live demo; Q&A and defense | First presentation session |
| 11 | Mon Nov 16 | **Final presentations (2 of 2).** Deliver a complete project and defend design decisions in response to questions. | Presentation; live demo; Q&A and defense | Last presentation session |
| 12 | **Fri Nov 20**, 6:30 – 9:15 PM, HAR 419 *(makeup session)* | **Exam review.** Consolidate and review the course's technical concepts ahead of the final exam. | Synthesis and review across all technical concepts; worked practice problems; Q&A | *Makeup session — not graded for participation; no graded assessment* |
| 13 | Mon Nov 23 | **Final exam.** Demonstrate independent understanding of the course's technical concepts. | In-class, closed-book, administered via Examplify; no Generative AI | **In-class final exam** |
| — | Mon Nov 30 | *No class meeting.* | — | **Final project report due** (Blackboard) |

> **Calendar note:** Session 5 meets on a **Tuesday** (BU substitute Monday schedule); sessions 7 and 12 meet on a **Friday** evening, 6:30 – 9:15 PM in HAR 419 (makeup sessions, replacing the Mon Nov 30 and Mon Dec 7 meetings). The course concludes with the final exam on **Mon Nov 23**. The final project report is due **Mon Nov 30**, a day with no class meeting; there are no meetings in December.
