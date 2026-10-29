# Command Advisor

Stop memorizing slash commands. Command Advisor watches for natural workflow moments — a failing build, freshly written code, an upcoming commit — and offers the matching command you already have installed, with a one-click question. Nothing runs without your yes.

> توقّف عن حفظ أسماء الأوامر. الإضافة تقترح عليك الأمر المناسب في اللحظة المناسبة وتسألك قبل التشغيل.

## What's inside
- **Skill `command-advisor`**: matches the moment to your installed commands, skills and agents, and asks via a question card.
- **SessionStart hook**: adds a one-line reminder at startup, after `/clear` and after compaction, so the advisor still fires when you have so many skills that Claude Code drops its description from the skill listing.
- **Command `/command-advisor:commands`**: lists your dev-workflow commands by phase (plan → build → test → review → ship → other) and suggests what fits now. Pass `all`, a phase (`review`), or a plugin name to change the scope.

Works with any commands you have: your own `~/.claude/commands`, and plugins like agent-skills or everything-claude-code. It never invents commands that aren't installed.

## Install
```
/plugin marketplace add OsamaA140/command-advisor
/plugin install command-advisor@command-advisor
```

## Behavior
- One suggestion per moment, recommended option first.
- Commands that commit, delete, or deploy are flagged in the question.
- Decline once and it won't nag about that command again in the session.
- Say "stop suggesting commands" to turn it off for the session.
- Your own rules win: if your CLAUDE.md or rule files say to run something without asking, the advisor doesn't ask about it.
- If nothing installed fits, it doesn't ask.

## Many skills installed?
Claude Code fits skill descriptions into a budget of about 1% of the context window. Past that budget it drops the descriptions of your least-used skills, so Claude stops matching them to your requests. To give all of your skills room, you can:
- raise the budget with the `skillListingBudgetFraction` setting (e.g. `0.02`), or
- set skills you never use to `"name-only"` in `skillOverrides`.

Run `/skill-doctor` to see which skills cost the most and which you never use.

## License
MIT
