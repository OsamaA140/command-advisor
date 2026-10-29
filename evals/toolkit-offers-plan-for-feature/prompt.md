---
description: A new non-trivial feature request should get a plan offer before any code.
expected_outcome: Advisor offers /devkit:plan; doesn't start implementing or run it.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

Let's add multi-currency support to the checkout: prices, totals, and refunds all need it.
