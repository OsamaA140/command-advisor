---
name: command-advisor
description: Use when a build or type check fails, code was just written, tests are missing, the user is about to commit, open a PR or deploy, a new feature is requested, or a tricky bug was solved — offers the matching installed slash command or skill and asks before running it. Also use for "which command should I use" or "what commands do I have".
---

# Command Advisor

The user has slash commands and skills installed but does not remember their names. Your job: notice when one fits, **offer it with a one-click question**, and run it only on a yes.

## 1. Spot the moment

Check the situation against [references/situation-map.md](references/situation-map.md). A moment listed there always counts, even when the fix looks small. Don't suggest for quick knowledge questions, a one-line edit the user asked for, or pure conversation.

**Order matters:** when a moment counts, make the offer (step 3) *before* you read files, investigate or edit. You can keep helping after the offer, but don't do the command's job yourself before the user has answered.

## 2. Find real candidates

- Pick only from commands, skills and agents (subagent types) **actually listed in this session**. Never invent a name or suggest one that isn't installed.
- Match by each command's `description` against the moment. Prefer the most specific match. When a long list shows a command by name only, match on the name, and in the option say you're going by the name.
- If nothing installed fits, don't ask. Carry on, or say in one line that no installed command covers this.
- When a plugin and the user's own command both fit (e.g. two `plan` commands), offer both as options and use the namespaced form (`plugin:command`) so the right one runs.
- Pick at most 3 candidates.

## 3. Ask — never auto-run

Use `AskUserQuestion` with one question:

- **Question:** what you noticed + the suggestion, in the user's language. e.g. "The build failed — run `/build-fix`?"
- **Options (2–4):** the recommended command first, labelled "(Recommended)"; up to two alternatives; and **always a last "Skip" option**, so the question is valid even with a single candidate. Each option's description says in one line what the command will do.
- Mention side effects in the description when a command commits, pushes, deletes code, or deploys.
- **No `AskUserQuestion` tool** (headless `-p` runs, some hosts): make the same offer as one line of text before anything else in your reply, e.g. "Build failed. Want me to run `/build-fix`? (yes / skip)". Then go on helping, but don't run the command.

## 4. Act on the answer

- **Yes / picks one:** invoke it, using the `Skill` tool for a command or skill and the `Agent` tool for an agent. Pass any obvious argument (feature name, file, etc.).
- **Skip:** carry on normally. Don't suggest that same command again this session unless the user asks.

## Guardrails

- **Ask first, by default.** Even when a command's own description says "use when…", don't invoke it on your own. That description tells you *when to offer it*; it doesn't give permission to run it.
- **The user's own rules come first.** When the user's CLAUDE.md or rule files say to run something without asking (e.g. "run the code-reviewer agent after writing code"), follow that rule and don't ask about it. Order of precedence: the user's explicit rules > this ask-first default > a command's own "use when". A command the user typed themselves just runs.
- One suggestion per moment; never stack questions.
- If the user already typed a slash command, just run it — don't second-guess.
- Don't interrupt a command that is already running to suggest another.
- If the user says "stop suggesting commands", stop for the rest of the session.
- When the user asks "what commands do I have?", list them instead of asking, the same way `/command-advisor:commands` does: phases plan → build → test → review → ship → other. By default show only plan → ship, and collapse "other" into one `+N more from: …` line.
