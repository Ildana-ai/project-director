# START - Interview and Build a New Project

You are the AI running this file. Your job, in order: interview the user, read back what you heard, build a new project repo per `MAP.md`, install the Project Director charter from `DIRECTOR.md`, report, and hand off.

Rules for this whole process:

- **Ask ONE question at a time.** Ask it, wait for the answer, then ask the next. Never stack questions or paste the whole list. The user should never be looking at more than one question.
- With each question give a short line of guidance: why it matters, and an example answer. Most people have not thought about this before and a blank prompt stalls them.
- Make no guesses and no assumptions. If an answer is vague, ask a follow-up before moving on.
- If the user does not know, say what you would pick and why, and let them accept it. Never leave them stuck.
- Keep it conversational. This is an intake conversation, not a form.

## Step 1 - Interview

Open with: "Running START.md to set up a new project. I'll ask a handful of questions, one at a time. Answer in plain language, and say 'not sure' any time you want me to recommend something."

Then work through these in order, one per turn.

**1. What should the project be called?**
Guidance: short and repo-safe, lowercase with hyphens, no spaces. It becomes the folder and repo name. Example: `client-portal`, `q3-tax-packet`.

**2. What is this and why does it exist?**
Guidance: one or two sentences, like you're telling a colleague. The "why" matters more than the "what", it's what keeps the project pointed the right way months from now. Example: "A scheduling tool for the front desk, because they're double-booking rooms on paper."

**3. What does done look like?**
Guidance: something you could point at and say yes, that's finished. Specific beats ambitious. Example: "Staff can book a room from their phone and see conflicts before they save." If they answer vaguely ("make it good"), push once for something checkable.
Then ask the follow-up: **"And what is deliberately NOT part of this?"** Guidance for them: naming what you're not building is as useful as naming what you are. It stops the project sprawling and stops the same argument three months from now. Example: "no mobile app, no payments." "Nothing yet" is a fine answer.

**4. Is there a deadline or any milestones?**
Guidance: a real date if one exists, otherwise "none". Fine to say none, it just changes how the plan is shaped.

**5. Is this a BUILD or a DELIVERABLE?**
Guidance: a BUILD is constructed over phases and keeps evolving (an app, a product, a system). A DELIVERABLE is one artifact you finish and hand over (a proposal, a report, a packet). Phases mean BUILD, a deadline-shaped document means DELIVERABLE. Read their earlier answers, say which one you think it is and why, and let them confirm or correct you.

**6. Where do your code projects live on this machine?**
Guidance: the folder you keep repos in. The project gets created as `<that folder>/<project-name>/`. Example: `~/Projects` or `~/Lab/GitHub`. If they don't know, ask them to check where an existing project sits, and warn that scattering repos across Documents, Desktop, and elsewhere is how people lose track of them.

**7. Create a private GitHub repo and push it, or keep it local for now?**
Guidance: private GitHub is the default and needs the `gh` command line tool signed in. Local-only is fine and can be pushed later. Never public unless they explicitly ask for public.

**8. Model plan, confirm or adjust.**
Guidance: state the default plainly, then ask if it works. The default: your strongest model acts as Project Director and spends its thinking on planning, decisions, and review. It hands the menial work (research sweeps, boilerplate, bulk edits, running tests) to cheaper models, in parallel where the tasks don't depend on each other. That keeps the expensive model's budget on judgment. Most people should take the default.

**9. Records: this project only, or system-wide?**
Guidance: explain first, then ask. Every project built here gets a handoff file and a decision log, that's what lets a brand-new chat pick the work up cold. The question is only whether you also want that habit written into your global AI instructions so every future project does it too. Default is this project only.

**10. What is it built with, and what is off-limits?**
Guidance: two things in one. First, the stack if you know it: languages, frameworks, hosting, and the one command to run it locally. Second, any constraints the Director must respect: platforms, budget, privacy, tools you refuse to use. Example: "Python and SQLite, run with `python app.py`, has to work offline." Either half can be "don't know yet", and the Director will write TBD rather than guess. Never invent a stack they did not name.

**11. Anything else it should know before starting?**
Guidance: open door. Context, history, preferences, a warning about the client. Anything they'd tell a new hire on day one.

## Step 2 - Readback

Play back the full setup in a few lines: name, purpose, type, done-criteria, out of scope, deadline, location, GitHub choice, model plan, records scope, stack and constraints. Ask: "Did I miss anything, or do you want to add anything?" Build only after a clear yes.

## Step 3 - Build

1. Create `<repos-folder>/<project-name>/`.
2. Scaffold it per `MAP.md`, using the profile chosen in the interview. Fill every file with real content from the interview answers. No placeholder text left behind.
3. Generate the new repo's `CLAUDE.md` from `DIRECTOR.md`: replace every `{{PLACEHOLDER}}` using the placeholder key at the bottom of that file. Write `TBD` for anything the user did not decide, never invent an answer. Set the date to today and the stage to "building". Keep the finished file under 200 lines. If the user's agent reads a different instruction file (for example `AGENTS.md`), use that name instead.
4. Write `.gitignore` BEFORE the first commit: secrets, `.env`, `node_modules/`, `.DS_Store`, `~$*` Office lock files, plus anything stack-specific.
5. `git init`, add all, first commit.
6. If GitHub was chosen: `gh repo create <project-name> --private --source=. --push`. If `gh` is missing or not authenticated, say so plainly and leave the repo local. Do not work around it.
   Then fill the repo URL into the References section of `CLAUDE.md`, or write "local only for now".
7. If system-wide records were chosen: show the user the exact lines you intend to append to their global AI instruction file, get a yes, then write them.

## Step 4 - Report and hand off

Tell the user:

- Who you are: model name and version.
- What you built: the absolute path and the file list.
- The repo URL, if pushed.

Then close with: "Ready. Open `<absolute path>` in a new chat window and the Project Director will introduce itself and take it from here."
