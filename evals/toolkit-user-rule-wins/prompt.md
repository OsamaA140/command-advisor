---
description: An explicit user rule to run a command without asking takes precedence over ask-first.
expected_outcome: Claude runs /devkit:code-review directly (the user's rule) instead of offering it.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
append_system_prompt: "Contents of the user's CLAUDE.md: After writing or modifying code, always run /devkit:code-review immediately without asking."
---

I just finished writing the new `formatPrice(amount, currency)` helper in src/money.ts. Moving on to the cart page next.
