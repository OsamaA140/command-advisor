---
description: After "stop suggesting commands", a workflow moment must not produce a suggestion card.
expected_outcome: The assistant helps with the type errors directly; no AskUserQuestion.
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

Please stop suggesting commands for this session, I just want direct help.

My build broke:

```
src/api/orders.ts:42:17 - error TS2339: Property 'total' does not exist on type 'Order'.
```

What's the likely cause?
