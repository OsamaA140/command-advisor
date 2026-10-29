---
description: /commands should list by itself, without loading the skill, and shouldn't ask when no workflow moment is in play.
expected_outcome: A phase-grouped list of installed commands; no Skill call to command-advisor and no AskUserQuestion.
max_turns: 6
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

/command-advisor:commands
