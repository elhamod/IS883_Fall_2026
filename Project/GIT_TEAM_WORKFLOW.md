# Working as a team in GitHub and VS Code

This guide takes your team from a GitHub account to a shared repository where everyone commits their own work
without overwriting anyone else's. Follow it on your own, in order. Everything happens in **VS Code** or on the
**GitHub website** — there is one copy-paste step in VS Code's terminal panel (step 1.3), and nothing else is typed.

**Why it matters for your grade.** The project directives (§6.4) require that **every member commits their own work
from their own GitHub account**. Your commit history is how we see who did what, and the workflow below produces it as
a side effect.

> **The one-line version:** never work directly on `main`. Each task gets its own **branch**; you try it in a test app
> deployed from that branch; when it works, you open a **pull request**; a teammate checks it and **merges** it into
> `main`. Your team's real Streamlit app runs from `main`, so `main` always works.

---

## Official videos — watch these first (about 25 minutes total)

All are from the official GitHub and Visual Studio Code YouTube channels.

| Watch | What it shows | Used in step |
| --- | --- | --- |
| [A brief introduction to Git for beginners](https://www.youtube.com/watch?v=r8jQ9hVA2qs) — GitHub | What a commit, a branch and a merge are | background |
| [How to use Git and GitHub in VS Code](https://www.youtube.com/watch?v=NFjz1AGKA4c) — GitHub | Cloning, committing and pushing from VS Code | 2, 3 |
| [Using Git with Visual Studio Code (Official Beginner Tutorial)](https://www.youtube.com/watch?v=i_23KUAEtUM) — VS Code | The Source Control panel, branches, the diff view, publishing | 3 |
| [How to create a pull request in 4 min](https://www.youtube.com/watch?v=nCKdihvneS0) — GitHub | Opening a pull request | 3.6 |
| [How to merge a pull request](https://www.youtube.com/watch?v=FDXSgyDGmho) — GitHub | Reviewing and merging, and what a conflict looks like | 3.6, 4 |
| [How to use GitHub issues and projects](https://www.youtube.com/watch?v=c67GaAkf1BE) — GitHub | The project board (skip the parts about issues — you will not need them) | 5 |

Written references: [VS Code — Source control](https://code.visualstudio.com/docs/sourcecontrol/overview) ·
[VS Code — Resolve merge conflicts](https://code.visualstudio.com/docs/sourcecontrol/merge-conflicts)

---

## 1. Set up once — every team member

1. **Install Git** from [git-scm.com/downloads](https://git-scm.com/downloads). On Windows, accept every default in the
   installer. On a Mac, VS Code offers to install it the first time you open the Source Control panel.
2. **Install VS Code** from [code.visualstudio.com](https://code.visualstudio.com/). Open it, click the **Accounts**
   icon (the person, bottom-left) → **Sign in with GitHub**, and approve in the browser.
3. **Tell Git who you are.** VS Code has no menu for this, so it is the one copy-paste step: in VS Code choose
   **Terminal → New Terminal**, and in the panel that opens at the bottom paste these two lines, one at a time, with
   your own name and **the email address your GitHub account uses** (GitHub → **Settings → Emails**), pressing Enter
   after each:

   ```bash
   git config --global user.name "Your Name"
   ```

   ```bash
   git config --global user.email "you@bu.edu"
   ```

   You can close the terminal panel afterwards; you will not need it again. This is what links each commit to *your*
   GitHub account. If the email does not match your GitHub account, your commits show up as an unknown author and do
   not count as yours.

## 2. The team repository

**If your team has not created its repository yet**, one person does it now: on GitHub, **+ → New repository** →
name it after your project → **Public** or **Private** → tick **Add a README file** → **Create repository**.
**If it already exists**, skip to the collaborators below — check that each one is there.

1. **Add collaborators:** repository **Settings → Collaborators → Add people**, one at a time:
   - every teammate;
   - the instructor, GitHub username **`elhamod`**;
   - the TA, Samuel, by email **`samuelbc@bu.edu`**.

   Each person must **accept the invitation** (from their email or github.com/notifications) before it takes effect.
   A teammate who has not accepted cannot push.
2. **The Gemini key never goes in the repository** — not in a `.py` file, not in any other file. It lives only in
   Streamlit Cloud's **Secrets** box (step 3.4). **If a key is ever committed, revoke it immediately** in
   [Google AI Studio](https://aistudio.google.com/) and make a new one. Deleting the file afterwards is not enough:
   the key stays in the repository's history.
3. **Every teammate clones it** (step 3.1) — including the person who created it.

## 3. The everyday loop — one task at a time

### 3.1 Get the repository onto your laptop (first time only)

VS Code → **Source Control** icon on the left (the branching-lines icon) → **Clone Repository** →
**Clone from GitHub** → pick your team's repository → choose a folder (**not** inside OneDrive, Dropbox or iCloud —
syncing software fights with Git) → **Open** when asked.

### 3.2 Start from an up-to-date `main`

Look at the **branch name** at the bottom-left of the VS Code window. If it does not say `main`, click it and choose
`main`. Then click **Sync Changes** in the Source Control panel (or the circular-arrows icon next to the branch name)
to download everything your teammates merged.

**Do this every time you sit down to work.** Most conflicts come from starting on an old copy.

### 3.3 Create a branch for your task

Click the branch name at the bottom-left → **Create new branch…** → type a short name for the task, such as
`chat-history` or `your-name-prompt-fix`. Press Enter. The bottom-left now shows your branch: everything you do from
here happens on it, not on `main`.

> Forgot and already edited files on `main`? Create the branch now — uncommitted edits come with you.

### 3.4 Commit, then try your branch in its own test app

**Commit — small and often.** In the **Source Control** panel you see every file you changed; click one to see exactly
what changed.

1. Hover a file and click **+** to **stage** it (include it in this commit). Stage only files that belong to this task.
2. Type a message that says *what* changed and *why* — `Keep chat history between turns so follow-up questions work`
   beats `update`.
3. Click **Commit**, then **Publish Branch** (the first time) or **Sync Changes** (after that) to upload to GitHub.

**Try it from your branch, not from `main`.** The first time you work on a branch, deploy a test app from it:

1. Go to [share.streamlit.io](https://share.streamlit.io) → **Create app** → deploy from GitHub.
2. **Repository:** your team's repository. **Branch:** *your* branch, not `main`. **Main file path:** your app's file.
3. **Advanced settings → Secrets:** paste the Gemini key the same way you did in Session 3. Click **Deploy**.

Every time you sync new commits to your branch, the test app updates by itself. Keep committing and trying until the
task works. Your teammates' real app on `main` is untouched the whole time.

### 3.5 When the task works — open a pull request

On your repository's GitHub page, a yellow banner appears: **Compare & pull request** — click it. (No banner? Go to
**Pull requests → New pull request**, set *compare* to your branch.)

- **Title:** what the change does.
- **Description:** one or two sentences, plus **the link to your branch's test app**, so the reviewer can try it.
- **Reviewers** (right side): pick a teammate. Click **Create pull request**.

### 3.6 A teammate reviews and merges

The reviewer opens the pull request → **Files changed** to read the change, opens the test app link to try it, and
then either leaves a comment or clicks **Review changes → Approve**. Then **Merge pull request → Confirm merge**, and
**Delete branch** (it has done its job).

**Rule of thumb:** nobody merges their own pull request unless a teammate has approved it. Reviewing is how the rest of
the team learns what changed.

### 3.7 Clean up, back to `main`, and repeat

- **Delete the branch's test app:** [share.streamlit.io](https://share.streamlit.io) → the **⋮** menu next to the
  app → **Delete**.
- In VS Code, switch to `main` (bottom-left) and **Sync Changes**. You now have everyone's merged work.
- Start the next task at step 3.3.

## 4. When two people changed the same lines — merge conflicts

**You will hit one; it is normal.** GitHub shows *This branch has conflicts that must be resolved* on the pull request,
and the merge button is greyed out.

1. In VS Code, make sure you are on **your** branch (bottom-left).
2. Bring `main` into your branch: **View → Command Palette…**, type `Git: Merge`, choose it, then choose `main`
   (or `origin/main`).
3. Files with conflicts are marked **!** in the Source Control panel. Open one and click **Resolve in Merge Editor**.
4. For each conflict, choose **Accept Incoming** (theirs), **Accept Current** (yours), or both, and check the result
   at the bottom. **If it is not your code, ask the teammate who wrote it** before throwing it away.
5. Click **Complete Merge**, then **Commit**, then **Sync Changes**. Check your branch's test app still works; the pull
   request on GitHub becomes mergeable again.

**How to have fewer conflicts:**
- Sync `main` before you start (step 3.2) and merge pull requests the same day they are opened.
- Keep tasks small, and split work by file where you can — one person on the prompt code, another on the UI.
- Do not reformat or re-indent a whole file as part of a task; it turns every line into a conflict.
- Jupyter notebooks conflict badly. Give each notebook one owner.

## 5. The project board — who is doing what

Directives §5.7 require a **project board** that shows your work moving over the weeks. Keep it simple: plain task
cards that you move by hand. **No issues, and nothing to connect to your code.**

1. **Create it once (one person):** your repository → **Projects** tab → **Link a project → New project** → choose
   the **Board** template → name it → **Create project**. It starts with three columns: **Todo**, **In Progress**,
   **Done**.
2. **Add the fields once:** on the board, **+** (new field) → add **Owner** (text), **Start date** and **End date**
   (date), and **Priority** (single select: High / Medium / Low).
3. **Add a task:** click **+ Add item** at the bottom of the **Todo** column, type the task in plain words
   (`Chat history between turns`), press Enter. Click the card and fill in its owner, dates and priority.
4. **Move it by hand:** drag the card to **In Progress** when you create its branch (step 3.3), and to **Done** when
   its pull request is merged (step 3.6).

A card per task, updated by whoever owns it, is all that is needed — the board's history is what we look at. Link the
board in your workshop checkpoint and in your report (directives §4.3, §6.1).

## 6. Your team's real app runs from `main`

Deploy your team's Streamlit Community Cloud app from the repository's **`main`** branch. **Every merge redeploys it**,
which is why every change is tried in a branch test app and reviewed before it reaches `main`.

## 7. Before you present — the `presentation` release

**Why, when `main` already deploys itself:** you keep working after you present — the report's *Response to feedback*
section (§6.1) is built from commits made *after* the presentation, so `main` keeps changing until the report is due.
The release freezes a copy of the code **exactly as it was when you presented**, and that frozen copy is what the
presentation, demo and build-quality grades are marked against (§6.4). Without it, nobody can tell which version you
presented.

GitHub → **Releases** → **Draft a new release** → tag name `presentation` → **Publish release**. Do it after your last
pull request is merged into `main`, before you walk up to present.

## 8. Quick fixes

| What you see | What to do |
| --- | --- |
| *Make sure you configure your user.name and user.email* | Do step 1.3. |
| *Can't push refs to remote* / *rejected* | Someone pushed first. Click **Sync Changes**, then try again. |
| *Permission denied* / *403* when pushing | You have not accepted the collaborator invitation (step 2.1), or you signed VS Code into a different GitHub account. |
| Your commits show an unknown author on GitHub | The email in step 1.3 does not match your GitHub account. Fix it; new commits will count. |
| You committed straight to `main` by mistake | Tell your team. If not yet synced: create a branch now (step 3.3) — the commit moves with you. |
| The test app does not show your latest change | Did you **Sync Changes** after committing? Is the test app deployed from *your* branch? |
| Streamlit says the key is missing | The key goes in Streamlit Cloud → your app → **Settings → Secrets**, not in the repository. |
| Folder is inside OneDrive and files keep changing | Move the clone somewhere outside the synced folder and clone again. |
