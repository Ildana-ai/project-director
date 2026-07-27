# MAP - The Structure and What Every File Is For

Every project gets the core. One profile goes on top, chosen by project type in the interview.

## Core (every project)

```
<repos-folder>/<name>/
  README.md      one paragraph: what this is and why, plus current state
  HANDOFF.md     the resume point: what just happened, what is next, open questions.
                 Updated at the end of every working session. This file is what lets a
                 brand-new chat window pick the project up cold.
  CLAUDE.md      the Project Director charter, generated from DIRECTOR.md. Carries the
                 standing brief any AI reads before touching the project: what this is,
                 the goal and what is out of scope, the stack and how to run it, the
                 decisions index, a map of the files, and external references. Dated at
                 the top, kept under 200 lines
  .gitignore     secrets and junk, written before the first commit
```

## BUILD profile (constructed over phases)

```
  ROADMAP.md                    the phased plan: checkboxes, current status snapshot, next tasks
  docs/PROJECT-BIBLE.md         the deep context: who/what/when/where/why/now, decisions made
                                and their reasoning, tools chosen, dead ends (so they are not
                                retried), glossary
  docs/DECISIONS-AND-TESTS.md   only if the project has tests: decision log plus a
                                chronological test log
```

Optional, on request: a `binder/` folder with a generated HTML status binder for humans who want a pretty view. The Director can build one when asked. Not created by default.

## DELIVERABLE profile (one-shot artifact)

The artifact is the product. No roadmap, no binder.

```
  STATUS.md    state (draft / submitted / won / lost), deadline, submission checklist,
               what is left
```

A deliverable may still get a light `docs/PROJECT-BIBLE.md` if it accumulates decisions worth remembering.

## Choosing

Phases mean BUILD. A deadline-shaped artifact means DELIVERABLE. Do not force roadmap ceremony onto a one-shot artifact.

## Gotchas (learned the hard way)

- Secrets and `node_modules/` must be gitignored before the first commit or they end up on the remote.
- Office apps drop `~$*.docx` lock files into folders; gitignore them.
- `HANDOFF.md` only works if it is actually updated every session. The Director owns that.
- Private by default. Public is a decision, never a default.
