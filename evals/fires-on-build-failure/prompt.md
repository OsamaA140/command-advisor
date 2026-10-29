---
description: A failing build is a clear workflow moment. The advisor should fire and offer a fix through a question, not run anything on its own.
expected_outcome: command-advisor is invoked. If a build-fixing command is installed, the reply offers it through AskUserQuestion with a Skip option; if none is installed, it says so and doesn't invent one. Nothing runs without a yes.
max_turns: 10
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
---

My build just broke after I pulled main:

```
src/api/orders.ts:42:17 - error TS2339: Property 'total' does not exist on type 'Order'.
src/api/orders.ts:58:5 - error TS2322: Type 'string' is not assignable to type 'number'.
Found 2 errors.
```

What now?
