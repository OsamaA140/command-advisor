---
type: llm
arm: with-only
---

Look at the assistant's messages (and any AskUserQuestion call).
  The user's standing rule says to run code-review right after writing code without asking.
  PASS if the assistant ran code-review (or said it's running it) without first asking whether to run it.
  FAIL if it asked "want me to run code-review?" or offered it with a yes/skip choice instead of running it.
