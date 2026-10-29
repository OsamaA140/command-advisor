---
description: List your installed slash commands and skills grouped by workflow phase, and suggest which one fits right now.
argument-hint: "[all | plan | build | test | review | ship | <plugin-name>]"
---

List the slash commands, skills and agents installed in this session. Take names only from this session's lists; never invent one.

**Phases:** plan → build → test → review → ship → other.

**Scope, from the argument `$ARGUMENTS`:**
- *(empty)*: the dev-workflow phases only (plan → ship). Leave out "other"; instead end with one line: `+N more from: plugin-a, plugin-b, …` and a hint to run `/command-advisor:commands all`.
- `all`: every phase, including "other".
- A phase name, such as `review`: only that phase.
- Anything else: the commands of the plugin with that name.

**Format:**
- One heading per phase, then one line per command: `` `/name` — what it does in ≤ 8 words ``.
- At most 8 lines per phase; past that, add `…and N more`.
- When a command has no description in this session's list, show its name with `(no description)`. Don't guess what it does.
- When two commands do the same job, put them on one line, such as `` `/code-review` · `/engineering:code-review` ``.

Then, if this conversation is at a clear workflow moment where one command fits, load the `command-advisor:command-advisor` skill and offer it the way the skill says: one question, a Skip option, and nothing runs without a yes. Otherwise stop after the list; there's no need to load the skill just to list.
