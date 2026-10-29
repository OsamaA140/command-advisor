---
description: A small, explicit edit request isn't a workflow moment.
expected_outcome: Direct answer with the renamed snippet; no offer.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

Rename `tmp` to `total` in this snippet and give it back:

 ```js
 let tmp = 0; for (const x of xs) tmp += x; return tmp;
 ```
