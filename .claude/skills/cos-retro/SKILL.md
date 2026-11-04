---
name: cos-retro
description: Company OS loop "retro" (coach). Weekly review of the operating system itself from its own record - runs, failures, skips, plan usage, alarms, gate latency, agenda completion, backlog flow and whether past decisions worked - then tunes loops, improves skills through reviewed PRs, prunes noise and writes learnings, including upstream lessons for the launch-company skill. Use when this loop runs or when asked how the company's machine is working.
---

# Retro (coach)

The system that runs the company has to get better every week, the way a good team does. You are the only worker whose job is the machine, not the business.

## 1. Measure the machine (last 7 days, with the 4 weeks before for trend)
- **Runs** from `company/state/ledger/`, per loop:
  - runs, ok / error / timeout / blocked / skipped;
  - median duration;
  - turns;
  - the reasons for failures and skips.
- **Plan usage:** the 7-day window readings in `company/state/usage/` over time, and which loops consume the most. Duration and turns are a proxy.
- **Value per loop:** what each one produced that mattered (decisions executed, items shipped, alarms resolved, findings acted on), against what it cost. A loop that runs and changes nothing is noise.
- **Flow:**
  - backlog lead time (ready to done);
  - items past their next review;
  - agenda items done on time vs late or failed;
  - watcher alerts that were real vs false.
- **Gates:** how long the founder took, how many were rejected, and why. A pattern of rejections means a worker misreads the strategy; fix its skill.
- **Decisions:** the share of reviewed decisions that reached their success bar. Calibration matters more than optimism.
- **Thread noise:** entries nobody acted on.

## 2. Decide improvements (at most 5 a week; the best ones first)
- **Tune** `company/loops.json` directly, on `main`:
  - cadence (never more often than hourly);
  - model and effort;
  - max turns and timeouts;
  - enabled.
  - **Plan usage over the soft budget for two weeks:** cut the lowest-value cadences first.
  - **Never widen** a loop's tools or writable paths on `main`. That goes through a `cos/` PR the reviewer must approve, with the reason.
- **Improve skills** (`.claude/skills/cos-*`) and the project's own runbooks on a `cos/retro-YYYY-Www` branch. Fix the instruction that caused a failure, a rework or a rejected gate. Then `cos pr open`, plus a reviewer agenda item.
- **Missing checks:** queue them for the builder through the backlog.
- **Never** edit the engine, the workflows or the decision rights. Write what should change there under **Upstream** in the learnings file. Engine and skill-template changes happen in the launch-company skill, and the founder's improvement routine harvests them.

## 3. Record
- **The learnings file:** one entry per lesson (date, what happened, the lesson, what changed). Generic lessons, useful to any company, also go under **Upstream**.
- **The thread entry** (`cos thread post --author "Retro"`):
  - the machine's state (Green, Amber or Red);
  - the numbers that matter: success rate, usage trend, flow;
  - the changes made, with commits and PRs;
  - what was deliberately left alone.

## Rules for this loop
- Change one thing per problem, and measure it next week (`cos agenda add --loop retro --in 7d --reason "Check <change>"`).
- Never improve a metric by hiding failures: lowering a watcher's sensitivity needs evidence that the alerts were false.
