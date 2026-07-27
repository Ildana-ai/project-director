# Contributing

Thanks for looking. This kit is deliberately small: five markdown files that tell an AI coding agent how to interview you and scaffold a project. Keeping it small is the point, so the bar for adding things is high.

## Good contributions

- Fixes where the interview stalls, confuses people, or asks something in a way that produces bad answers.
- Support for another AI coding agent. The kit assumes an agent that can read files and run commands. If yours needs a different instruction filename or a different delegation mechanism, say so.
- Real reports of the scaffold producing something broken: a bad `.gitignore`, a missing file, a `gh` command that fails in a case we did not anticipate.
- Clearer wording. If a question needed re-reading, that is a bug.

## Things that will probably be declined

- New questions in the interview. Eleven is already a lot to ask someone before they have started. A new question has to earn its place by replacing one.
- Framework-specific or language-specific scaffolding. The kit stays generic on purpose.
- Automation that hides what the agent is doing. The user should be able to read every step before it runs.

## How to propose a change

Open an issue first for anything beyond a typo. Describe what happened, what you expected, and which agent and model you were running. Agreement on the problem before code saves everyone time.

For pull requests: one change per PR, explain the reasoning in the description, and confirm you actually ran `START.md` end to end with your change in place. This kit is instructions for a model, so the only real test is running it and seeing what the model does.

## Style

Plain language. Short sentences. No jargon where a normal word works. The files are read by both people and models, and both do better with clear prose than with clever formatting.
