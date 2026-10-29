---
description: With a build-fix command installed, a failing build should get an offer for it, not an auto-run.
expected_outcome: Advisor fires, offers /devkit:build-fix with a skip option, and doesn't run it.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

My build just broke after I pulled main:

 ```
 src/api/orders.ts:42:17 - error TS2339: Property 'total' does not exist on type 'Order'.
 Found 1 error.
 ```

 What now?
