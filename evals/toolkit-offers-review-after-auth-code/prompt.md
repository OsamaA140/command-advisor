---
description: Freshly written auth code is a review moment; the most specific command (security-review) should come first.
expected_outcome: Advisor offers /devkit:security-review (and maybe code-review), runs neither.
tags: [v2]
max_turns: 8
allowed_tools: [Read, Glob, Grep, Skill, AskUserQuestion]
plugins: ["../..", "devkit"]
---

I just finished writing this login handler, here it is:

 ```ts
 export async function login(req, res) {
   const user = await db.query(`SELECT * FROM users WHERE email = '${req.body.email}'`);
   if (user && user.password === req.body.password) {
     res.cookie("session", user.id);
     return res.json({ ok: true });
   }
   res.status(401).json({ ok: false });
 }
 ```

 Looks good to me. Next I'll wire it into the router.
