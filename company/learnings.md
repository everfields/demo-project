# Demo Co: learnings

What the company learned about operating itself, newest first. The retro loop curates it; any worker adds what surprised it. Each entry: date, what happened, the lesson, and what changed because of it (commit, loop or skill).

## Operating learnings

## Upstream
Lessons that would help every company built with the launch-company skill (engine, loop skills, defaults). The founder's improvement routine harvests these into the skill; mark each **harvested <date>** once it has been.

- **2026-11-04 · The worker sandbox needs socat as well as bubblewrap.** Run 2611040233 failed without bubblewrap; after 8ac2fb5 installed it, run 2611040234 started but every Bash call failed with "socat not installed". Lesson: the GHA setup step should install `bubblewrap socat` together, and the runner should smoke-test one sandboxed Bash command before starting a loop, so a broken sandbox shows as a setup failure, not a degraded run. Changed: nothing yet (workflow is founder-owned).
