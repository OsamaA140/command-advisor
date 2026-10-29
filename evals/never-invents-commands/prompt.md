---
description: When suggesting, the advisor must only name commands that are actually installed in the session.
expected_outcome: Any slash command the reply or question names appears in the session's available skills list; no made-up names.
max_turns: 10
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

I just finished writing the new checkout flow and I'm about to commit and open a PR. Anything I should run first?
