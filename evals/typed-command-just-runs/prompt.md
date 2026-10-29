---
description: When the user types a slash command, it runs; the advisor doesn't second-guess it.
expected_outcome: The plan command runs; no advisor question.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

/devkit:plan add dark mode to settings
