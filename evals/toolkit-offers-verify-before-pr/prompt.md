---
description: About to commit and open a PR, so verify should be offered.
expected_outcome: Advisor offers /devkit:verify before commit; doesn't run it.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

I'm done with the checkout feature. I'm about to commit and open a PR. Anything I should run first?
