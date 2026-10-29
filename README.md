# Command Advisor

Stop memorizing slash commands. Command Advisor watches for natural workflow moments — a failing build, freshly written code, an upcoming commit — and offers the matching command you already have installed, with a one-click question. Nothing runs without your yes.

> توقّف عن حفظ أسماء الأوامر. الإضافة تقترح عليك الأمر المناسب في اللحظة المناسبة وتسألك قبل التشغيل.

## What's inside
- **Skill `command-advisor`** — matches the moment to your installed commands/skills and asks via a question card.
- **Command `/command-advisor:commands`** — lists everything you have, grouped by phase, and suggests what fits now.

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

## License
MIT
