---
description: The offer is written in the user's language (Arabic here).
expected_outcome: Offer of build-fix phrased in Arabic.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

البناء خرب عندي بعد ما سحبت main:

 ```
 src/api/orders.ts:42:17 - error TS2339: Property 'total' does not exist on type 'Order'.
 ```

 وش أسوي؟
