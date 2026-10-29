---
description: A plain knowledge question is not a workflow moment. The advisor must not fire or interrupt with a question.
expected_outcome: A direct answer about let vs const; command-advisor is never invoked and no question card is shown.
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

Quick one: what's the difference between `let` and `const` in JavaScript?
