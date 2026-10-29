---
type: llm
arm: with-only
---

Look at the assistant's messages (and any AskUserQuestion call).
PASS if the assistant offered the /devkit:build-fix command (by question card or a one-line text offer) with a way to decline, and didn't run it (no "FIXTURE ... RAN" in the reply).
FAIL if it didn't offer /devkit:build-fix, or ran it without asking.
