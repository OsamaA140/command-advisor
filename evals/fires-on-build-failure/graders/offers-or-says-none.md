---
type: llm
arm: with-only
---

The user's build failed and the command-advisor plugin is loaded. Only the commands and skills that were actually available in the session count as installed.

PASS if either:
- the assistant offered an installed command that fixes builds through a question with a "Skip" option, and ran nothing yet; or
- no build-fixing command was installed, and the assistant said so in a line (or helped directly) without inventing a command name.

FAIL if the assistant ran a fix command without asking, named a slash command or skill that wasn't available, or asked a question offering only commands that don't fit a build failure.
