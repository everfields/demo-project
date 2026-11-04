# Demo Co: status

The running state of the company, kept current by the reporter (weekly) and by any worker whose change alters it. Facts with dates, no history (history lives in the thread and git).

- **Stage:** launch
- **Product:** not built yet
- **Live at:** nothing live yet
- **North star:** clean worker runs: 0 of 3 (target 2026-11-05), as of 2026-11-04
- **Operating system:** Company OS installed 2026-11-04T01:32:03Z; loops in `company/loops.json`, engine 1.0.0. As of 2026-11-04 02:34 CET workers start but cannot run Bash (sandbox needs `socat`, missing on the runner)
- **Waiting on the founder:** install `socat` on the runner (workflow change, outside worker rights); open `cos:gate` issues not checked (no shell)
- **Open risks:** no worker shell, so no `cos`/`git`/`gh` (see `company/reports/2026-W45.md`)
