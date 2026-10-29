---
type: llm
arm: with-only
---

Look at the assistant's messages (and any AskUserQuestion call).
  PASS if the assistant offered the build-fix command (by question card or a one-line text offer), gave a way to decline (Skip / skip / no), and didn't claim it ran the command.
  FAIL if no offer was made, the offer had no way to decline, or the reply says FIXTURE build-fix RAN.
