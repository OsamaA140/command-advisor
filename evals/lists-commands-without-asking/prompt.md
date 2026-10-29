---
description: Asking what commands exist should produce a grouped list, not a question card.
expected_outcome: command-advisor fires and the reply lists installed commands/skills grouped by workflow phase; no AskUserQuestion.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

I never remember my slash commands. What commands do I have?
