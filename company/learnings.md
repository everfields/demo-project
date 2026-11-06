# Demo Co: learnings

What the company learned about operating itself, newest first. The retro loop curates it; any worker adds what surprised it. Each entry: date, what happened, the lesson, and what changed because of it (commit, loop or skill).

## Operating learnings

- **2026-11-06 · A deliberate pause looks like an outage when the company resumes.** `company/PAUSE` ran from 2026-11-04 02:46 to 2026-11-06 21:55. The first pulse afterwards opened critical alarm #8 because the incident loop had never succeeded. Lesson: after any pause, run each loop or queue it before its `max_age_hours` runs out, counted from launch or from its last ok. Changed: backlog and retro were queued early; postmortem `company/incidents/2026-11-06-stale-incident-after-pause.md`.
- **2026-11-04 · The worker shell works after ebd1254.** Run 2611040240 ran `cos`, `git` and `gh` inside the sandbox. Before that, run 2611040234 was recorded as `ok` while it had no shell at all. Lesson: a ledger `ok` does not mean the run was healthy, so the north star count should also check that the run made tool calls. Changed: the W45 report counts that run as degraded.

## Upstream
Lessons that would help every company built with the launch-company skill (engine, loop skills, defaults). The founder's improvement routine harvests these into the skill; mark each **harvested <date>** once it has been.

- **2026-11-06 · The stale-loop sentinel should not count paused time.** In `sentinel()` (cos.mjs), `since = last_ok ?? launched_at` ignores `company/PAUSE`, so every loop that was due during a pause raises a false stale alarm on resume (alarm #8 was critical). Fix: use the later of `since` and the resume time, or give each loop one schedule period of grace after a resume. Changed: nothing upstream yet (the engine is outside worker rights).
- **2026-11-04 · The worker sandbox needs socat as well as bubblewrap.** Run 2611040233 failed without bubblewrap; after 8ac2fb5 installed it, run 2611040234 started but every Bash call failed with "socat not installed". Lesson: the GHA setup step should install `bubblewrap socat` together, and the runner should smoke-test one sandboxed Bash command before starting a loop, so a broken sandbox shows as a setup failure, not a degraded run. Changed: nothing yet (workflow is founder-owned).
