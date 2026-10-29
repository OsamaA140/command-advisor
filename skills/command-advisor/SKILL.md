---
name: command-advisor
description: Suggests the right installed slash command or skill at the right moment and asks before running it, so the user never has to remember command names. Use at natural workflow moments — a new feature or change is requested, a build or type check fails, code was just written, tests or coverage are missing, the user is about to commit, open a PR or deploy, a page is slow, or a tricky bug was just solved. Also use when the user asks "which command should I use", "what commands do I have", or seems unsure how to proceed.
---

# Command Advisor

The user has slash commands and skills installed but does not remember their names. Your job: notice when one fits, **offer it with a one-click question**, and run it only on a yes.

## 1. Spot the moment

Check the situation against [references/situation-map.md](references/situation-map.md). Only suggest at a clear workflow moment — not for quick questions, one-line edits, or pure conversation.

## 2. Find real candidates

- Pick only from commands and skills **actually listed in this session** (the available-skills list). Never invent a name or suggest one that isn't installed.
- Match by each command's `description` against the moment. Prefer the most specific match.
- When a plugin and the user's own command both fit (e.g. two `plan` commands), offer both as options and use the namespaced form (`plugin:command`) so the right one runs.
- Pick at most 3 candidates.

## 3. Ask — never auto-run

Use `AskUserQuestion` with one question:

- **Question:** what you noticed + the suggestion, in the user's language. e.g. "The build failed — run `/build-fix`?"
- **Options (2–4):** the recommended command first, labelled "(Recommended)"; up to two alternatives; and **always a last "Skip" option**, so the question is valid even with a single candidate. Each option's description says in one line what the command will do.
- Mention side effects in the description when a command commits, pushes, deletes code, or deploys.

## 4. Act on the answer

- **Yes / picks one:** invoke it with the `Skill` tool, passing any obvious argument (feature name, file, etc.).
- **Skip:** carry on normally. Don't suggest that same command again this session unless the user asks.

## Guardrails

- **Ask first, always.** Even when a command's own description says "use when…", don't invoke it on your own — that description tells you *when to offer it*, not permission to run it. The only exception is a command the user typed themselves.
- One suggestion per moment; never stack questions.
- If the user already typed a slash command, just run it — don't second-guess.
- Don't interrupt a command that is already running to suggest another.
- If the user says "stop suggesting commands", stop for the rest of the session.
- When the user asks "what commands do I have?", list the installed ones grouped by workflow phase (plan → build → test → review → ship) with one line each, instead of asking.
