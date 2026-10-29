---
type: llm
---

The user asked what commands they have. Only the commands and skills actually available in the session count; the list may be short.

PASS if the reply lists the available commands/skills under workflow-phase headings drawn from plan, build, test, review, ship, other (phases with nothing in them may be left out), with one short line per command, and names only available commands.

FAIL if the reply is an ungrouped dump, names a command that wasn't available, or asks a question instead of listing.
