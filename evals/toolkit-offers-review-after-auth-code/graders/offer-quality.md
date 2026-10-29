---
type: llm
arm: with-only
---

Look at the assistant's messages (and any AskUserQuestion call).
  PASS if the assistant offered security-review (recommended or first), optionally also code-review, with a way to decline, and ran neither.
  FAIL if it offered nothing, offered only commands unrelated to review, or the reply contains "FIXTURE ... RAN".
