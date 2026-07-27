# Security Policy

## Reporting a vulnerability

Email **hello@ildana.ai** with the details. Please do not open a public issue for a security problem.

Include what you found, how to reproduce it, and what an attacker could do with it. You can expect an acknowledgement within a few business days.

## Scope

This kit is markdown instructions for an AI coding agent. It ships no executable code, no dependencies, and no network calls of its own. The realistic risks are therefore about what the instructions cause an agent to do:

- Instructions that could lead an agent to write secrets into a repo, or to commit before `.gitignore` is in place.
- Instructions that could cause an agent to create a public repository when the user asked for private.
- Wording an attacker could exploit through prompt injection, for example if a project name or answer is crafted to change the agent's behavior.

Reports in those categories are genuinely useful. Report them.

## Out of scope

- Vulnerabilities in the AI agent, model, or `git`/`gh` tooling you run this with. Report those to their vendors.
- What an agent does with instructions you added or modified yourself.

## For users of this kit

The scaffold writes `.gitignore` before the first commit, and it defaults every new repository to private. If you see it do otherwise, that is a bug worth reporting.
