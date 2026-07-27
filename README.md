# Project Director

A project bootstrap kit for AI coding agents. Point Claude Code (or any AI coding agent) at this folder and it interviews you, builds a new project repo with a proven structure, and installs an AI Project Director inside it. Open that new repo in a fresh chat and your AI takes on the project manager role: it introduces itself, runs the project with you, and spins up cheaper sub-agents as needed for the grunt work, keeping your strongest model on judgment.

## What this kit does

- Interviews you about the project. Eleven questions, one at a time, each with guidance on why it matters and an example answer. No guesses, no assumptions, and it recommends an answer any time you say you are not sure.
- Reads the plan back to you and waits for your confirmation before touching anything.
- Creates the new project repo in the folder you name, with a private GitHub repo and push if you want one.
- Scaffolds a proven structure: a core every project gets, plus a BUILD profile (phased work) or a DELIVERABLE profile (one-shot artifact). See `MAP.md`.
- Generates the new repo's `CLAUDE.md` from the charter template. That file is what makes the next AI that opens the repo take on the project manager role: it introduces itself as your Project Director, states where things stand, and runs the project with you.
- Builds delegation in. During the project the Director spins up sub-agents as needed (for example Opus, Sonnet, or Haiku), in parallel when tasks are independent, and hands them the menial work.
- Reports who it is and what it built, then tells you where to point your next chat.

## What it does not do

- It does not write your project's actual content or code. That is the Director's job, with you, in the new repo.
- It does not create public repos. Private is the default and public requires your explicit request.
- It does not touch anything outside this folder and the repos folder you name.
- It does not send anything anywhere, except the optional push to your own GitHub.
- It does not lock you to a vendor. Built for Claude Code; any agent that can read files and run commands can follow it.

## Why it works this way

- **Chat windows die.** Context dies with them. Every project built here carries a `HANDOFF.md`, the resume point a brand-new chat can pick up cold.
- **Same skeleton every time.** Any AI, or any human, can navigate any of your projects without a tour.
- **Interview first, readback gate second.** The plan is yours, confirmed by you, before a single file is written.
- **Manager and workers.** The strongest model acts as Director and spends its budget on judgment: planning, review, decisions. For everything menial (research sweeps, boilerplate, bulk edits, test runs) it spins up cheaper sub-agents as needed and runs them in parallel.
- **Records are the product.** A handoff file and a decision log are built into every project because a project you cannot resume is a project you restart.
- **Private by default.** Publishing is a decision, never a side effect.
- **One layer, not three.** This is the project layer. Who you are and how you write belongs in your global AI instructions; the charter says so explicitly so it does not duplicate them.

## The default setup

Every project gets the core:

```
README.md      what this is and why, plus current state
HANDOFF.md     the resume point, updated every working session
CLAUDE.md      the Project Director charter
.gitignore     secrets and junk, written before the first commit
```

Then one profile on top. BUILD adds `ROADMAP.md` and `docs/PROJECT-BIBLE.md` (plus a decisions-and-tests log when there are tests). DELIVERABLE adds `STATUS.md` and skips the ceremony. Full detail and reasoning per file: `MAP.md`.

Model default: strongest available model as Director, cheaper models (for example Opus, Sonnet, Haiku) as parallel sub-agents. The interview confirms or adjusts this.

## Setup

1. Clone or download this repo. That is the whole install; the kit is markdown, no dependencies.
2. Have `git` installed.
3. Optional: GitHub CLI (`gh`), logged in, if you want the private GitHub repo created and pushed for you.

## Use

1. Open this folder in Claude Code (or your AI coding agent).
2. Say: `Run START.md`
3. Answer the interview and confirm the readback.
4. The AI builds the new repo and reports back.
5. Open the new repo in a fresh chat window. The Director introduces itself, states where the project stands, and proposes the next step.

Re-run `START.md` any time you want another project. The kit only ever creates; it never edits an existing project.

## Good to know

- Non-code projects work fine. A proposal, a report, a filing packet: those are DELIVERABLEs.
- The kit folder itself never becomes your project. Your project lives where your repos live.
- If `gh` is missing or logged out, the AI says so and leaves the repo local. Nothing silently fails.

## Files

- `START.md`, the script your AI follows: interview, readback, build, report, hand off.
- `MAP.md`, the structure it builds and what every file is for.
- `DIRECTOR.md`, the charter template that becomes the new repo's `CLAUDE.md`.

## Contributing

Issues and pull requests are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) first, it says plainly what usually gets accepted and what usually gets declined. Found a security problem? [SECURITY.md](SECURITY.md), and please do not open a public issue.

## License

MIT. Use it, fork it, ship things with it.

---

Built by [Ildana](https://ildana.ai).
