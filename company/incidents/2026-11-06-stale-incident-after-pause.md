# 2026-11-06 · Alarm #8: "incident has not succeeded for 67 h"

Severity: critical (the label comes from the loop's priority). Real impact: none. No users, money, data or SEO were affected. Demo Co is a sandbox with no production.

## What happened
The incident loop had never run when the pulse at 21:57 CET on 2026-11-06 checked it. The sentinel measures staleness from the last successful run, or from `company.launched_at` (2026-11-04 02:32 CET) if a loop has never succeeded. 67 h had passed against the 50 h limit, so it opened alarm #8 and queued this loop.

## Timeline (Europe/Madrid)
- 2026-11-04 02:32: Company OS launched (`launched_at`).
- 2026-11-04 02:46: the founder set `company/PAUSE` (a0115ae, "pause it after the live verification"). No scheduled loop runs while it is set.
- 2026-11-04, 05 and 06, 08:40: incident runs were due on schedule. All three fell inside the pause and did not run.
- 2026-11-06 21:55: the founder removed `company/PAUSE` in the 1.3.0 upgrade (32c12f9).
- 2026-11-06 21:57: the first pulse after the resume opened #8 (critical) and queued the incident loop.
- 2026-11-06 21:58: run 2611062158-incident-8c98 started, found the cause and wrote this.

## Cause
The founder's pause was deliberate. `sentinel()` in `company/engine/cos.mjs` (around line 2366) does not subtract time spent under `company/PAUSE` when it checks `max_age_hours`, so any loop that was due during a pause looks stale as soon as the company resumes. Nothing was broken.

## What fixes it
This run finishing `ok` gives the incident loop a `last_ok`. The next pulse then closes #8 by itself ("it succeeded again").

## What prevents it now
- The same false alarm would hit two more loops before their first scheduled run:
  - backlog: limit 120 h, so stale at 2026-11-09 02:32 CET. Its first run is Mon 2026-11-09 08:30.
  - retro: limit 192 h, so stale at 2026-11-12 02:32 CET. Its first run is Fri 2026-11-13 16:00.

  Both now have an early agenda run, and each run has real work: backlog has never triaged since launch, and retro has never reviewed the system.
- Reporter is fine: its last `ok` was 2026-11-04 02:41, its limit is 192 h, and it runs Mon 2026-11-09 09:00.
- Engine fix (upstream, outside worker rights): the sentinel should take `max(last_ok, launched_at, last resume from PAUSE)` as `since`, or skip the staleness check for a window after a resume. This is recorded in `company/learnings.md` under Upstream.

## What I could not verify
- The exact pause and resume times come from commit times, not from runner logs.
- That #8 closes by itself depends on this run being recorded `ok` and on the next pulse. A follow-up incident run in 1 d checks it.

## Correction (retro, run 2611062158-retro-70f5)
The cause above is incomplete. `incident` has priority `critical`, and the engine never holds a critical loop for `company/PAUSE` (in `run()` and in the pulse dispatch check). The pause alone would not have stopped it. It never ran because **no pulse ran at all**: the `Company OS pulse` workflow is `disabled_manually` (`gh workflow list`). The only pulses on record were started by hand, at 2026-11-04 01:32 UTC and 2026-11-06 20:57 UTC (`gh run list`), and neither came from the cron. So nothing checked the schedule between those two pulses, whatever its priority.
- With the pulse off and PAUSE set again at 21:58 (00dfda7), #8 could not close itself. Retro closed it with the evidence: incident `last_ok` 2026-11-06T20:59:39Z.
- The early runs queued above (backlog 2026-11-07, retro 2026-11-10) and the follow-up on #8 could not fire either. Without a pulse, the only time they would run is the next resume, all at once. Retro cancelled them because each was redundant (see the agenda notes).
- Lesson for the incident role: when a loop is stale, first check that the clock is running (`gh workflow list`, `company/state/pulse.json` `last_pulse`), and only then look at why the loop itself did not run.
