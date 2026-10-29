---
type: llm
arm: with-only
---

Look at every slash command or skill name the assistant suggested (in its text or in any AskUserQuestion options).

PASS if every suggested name is one that was actually available in the session (listed among the available skills/commands), or if it suggested no command and simply explained that none fits.

FAIL if it suggests a slash command or skill that was not available in the session (for example inventing `/verify` or `/code-review` when no such command was listed).
