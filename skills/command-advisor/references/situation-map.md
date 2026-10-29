# Situation → kind of command

Look for an installed command, skill or agent whose name or description matches the "Look for" column. The names below are common examples, not requirements. Agents run through the `Agent` tool; everything else runs through `Skill`.

| Moment | Look for a command that… | Common names | Common agents |
|---|---|---|---|
| Vague idea, no spec yet | writes a spec / interviews for requirements | `spec`, `interview-me`, `idea-refine` |  |
| New feature or non-trivial change requested | plans or breaks work into tasks | `plan`, `planning` | `planner` |
| About to implement a planned task | builds incrementally | `build`, `incremental-implementation` |  |
| Writing logic or fixing a bug | enforces test-first | `tdd`, `test-driven-development` | `tdd-guide` |
| Build or type check fails | fixes build errors | `build-fix` | `build-error-resolver` |
| Tests fail or behavior is unexpected | debugs root cause | `debug`, `debugging-and-error-recovery` |  |
| Code was just written or modified | reviews code | `code-review`, `review` | `code-reviewer` |
| Auth, user input, secrets or payments touched | security review | `security-review`, `security-audit` | `security-reviewer` |
| Coverage low or code added without tests | generates tests / coverage | `test-coverage`, `test` |  |
| Critical user flow added or changed | end-to-end tests | `e2e` | `e2e-runner` |
| Code works but is convoluted | simplifies | `code-simplify`, `simplify` |  |
| Unused code, exports or deps noticed | removes dead code | `refactor-clean` | `refactor-cleaner` |
| About to commit or open a PR | verifies build/types/tests | `verify` |  |
| Before a risky change | saves a checkpoint | `checkpoint` |  |
| Page slow, Core Web Vitals concerns | audits web performance | `webperf`, `performance-optimization` |  |
| Scripts, config or public API changed | updates docs | `update-docs`, `documentation` | `doc-updater` |
| Large structural change landed | updates architecture maps | `update-codemaps` |  |
| Preparing a release or deploy | runs a launch checklist | `ship`, `deploy-checklist` |  |
| Just solved a tricky problem | saves the pattern as a skill | `learn` |  |
