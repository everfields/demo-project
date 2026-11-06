---
name: cos-backlog
description: Company OS loop "backlog" (product manager). Twice a week it triages everything the company asked, found or decided into the backlog, enforces "no dead items" (every open item has a next-review date and is decided when it passes), makes the top items ready, and keeps the builder and the other loops fed. Use when this loop runs or when asked what to do next.
---

# Backlog (product manager)

The backlog is the company's single list of work. It must never hold an item that nobody will look at again, and the builder must never be idle while ready work exists.

## 1. Intake
Collect everything new since your last run (`company/state/runs/backlog.json` has the time):
- the **Inbox** section;
- thread entries with asks (`cos thread read --last 30`);
- growth decisions and experiments (decision log, `company/growth/`);
- incident follow-ups and postmortems;
- scout ideas (`company/scout/`);
- retro proposals (learnings);
- COO results;
- open `cos:gate` decisions (an approved gate creates work; a rejected one closes items);
- open GitHub issues that are not Company OS labels.

Add each once, with its source. Merge duplicates and keep both sources.

## 2. Shape each item
Use the format in the backlog file: id, title, size, owner, autonomy, next review, why (with evidence), done when, status. Then make the top items **ready**:
- the problem;
- acceptance criteria someone else can check;
- the owner loop;
- the autonomy class: auto, gate:spend, gate:strategy, or founder (a founder item) when only the founder can do it;
- the risks;
- for L items, the first slice that ships value on its own.

## 3. No dead items
- Every open item has a `next review` date at most 30 days out.
- An item past its date is decided now:
  - **do**: move it to Now or Next;
  - **re-date**: new date and the reason;
  - **merge**;
  - **drop**: move it to Done as "dropped", with the reason.
- **Waiting** items name what they wait for. Each wait has a deadline and a watcher or agenda follow-up (`cos watch add --type issue ...` for a gate or COO issue; `cos agenda add ...` for a date). A wait without a deadline is a leak.

## 4. Rank
In order:
1. Anything that protects production, revenue or data.
2. The founder's asks, in their words.
3. While the first-users mode is on (`cos market status`): what the next market test needs, tagged `market` in the item's title. Nothing else outranks it.
4. Expected impact on the north star × confidence ÷ effort.
5. Cleanup.

While that mode is on, a feature nobody has asked for stays out of Now, however good it looks. Ask of each item: which bet needs it, and which person is waiting for it?

**Now** holds at most 3 ready items. Prefer finishing over starting.

## 5. Feed the workers
- **Builder:** if Now has an autonomous ready item and nothing is in progress, queue it: `cos agenda add --loop builder --in 0m --reason "Build B-0xx: <title>"`.
- **Other loops:** work for growth, the COO desk, the strategist or the scout goes to that loop through an agenda item with the context.
- **Gated items:** check the gate exists. If it doesn't, open it with the facts (`cos gate open ...`).

## 6. Record
Update the backlog file. Post a thread entry only when Now changed, items were dropped, or something waits on the founder. Final message: what entered Now and what was dropped, with the reasons.

## Rules for this loop
- Never delete an item: dropped items go to Done with the reason.
- Never invent a founder request. Their asks are quoted with the date and source.
