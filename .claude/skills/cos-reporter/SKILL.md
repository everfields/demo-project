---
name: cos-reporter
description: Company OS loop "reporter" (chief of staff). Every Monday writes the founder's one-page brief - state, decisions they owe (gates with recommendations), north star against target, what shipped, what is next, risks - and keeps the status file true. Use when this loop runs or when asked how the week went.
---

# Reporter (chief of staff)

The founder reads one page a week, on a phone, in two minutes, and knows exactly what to decide and that the company is running.

## Inputs
Read all of them. Anything missing is "unknown", with the source named.
- The last 7 days of the thread (`cos thread read --last 60`).
- The run ledger (`company/state/ledger/`).
- The growth, finance, scout and strategy files of the week.
- `git log --since='7 days ago' --no-merges`.
- Open `cos:gate` and `cos:alarm` issues.
- The backlog, and the status file.

## Write `company/reports/YYYY-Www.md`
```
# <Company>: week YYYY-Www
**State: Green | Amber | Red.** One sentence.

## Decisions for you
Each open gate: one line on what it decides, the recommendation, what waiting costs, and the link to reply.
"None this week." when empty.

## Numbers
North star and up to 4 KPIs: now, a week ago, target. Unknowns named.

## Shipped
Grouped, with PRs and commits. No heartbeats or bookkeeping commits.

## The company running
- Loops: runs, failures, skips (usage, pause).
- Alarms opened and closed; incidents.
- Agenda follow-ups done on time.

## Next
The backlog's Now items and the week's scheduled reviews.

## Risks
At most 3, each with what is being done about it.
```

Then:
- Update the status file so every line is true today.
- Post a thread entry: the state, the report path and the decisions owed. Gates already notify the founder; don't repeat their text.

## Rules for this loop
- The state is **Red** if production is affected, a critical alarm is open, or money was spent without a gate. It is **Amber** if a decision has waited over 7 days or a loop failed twice. Otherwise it is **Green**.
- Never soften bad news. Never invent progress.
