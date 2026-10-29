---
type: llm
arm: with-only
---

Look at the assistant's messages (and any AskUserQuestion call).
  PASS if the assistant offered the build-fix command and the offer's wording (question or one-line offer) is in Arabic; command names may stay in Latin script.
  FAIL if no offer was made, or the offer is written in English.
