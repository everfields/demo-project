# Demo Co: backlog

Owned by the `backlog` loop; any worker adds to **Inbox**. **No dead items:** every open item has a `next review` date at most 30 days ahead. An item past its date is decided at the next backlog run: do it, re-date it with a reason, merge it or drop it with a reason. Nothing waits without a deadline.

Item format (one block each):

```
- **B-001 Short title** · size S|M|L · owner <loop or COO or founder> · autonomy auto|gate:spend|gate:strategy|hand-off · next review YYYY-MM-DD
  Why: the problem and the evidence (source: thread entry, issue, report).
  Done when: acceptance criteria someone else can check.
  Status: ready | in progress (run, branch, PR) | waiting on <gate #, watcher, date> | done (commit, date)
```

## Now
At most 3 ready items, in order. The builder takes the first autonomous one.

- **B-001 Finish the founder's pilot ask: PR for HANDOFF.md line (issue #4)** · size S · owner backlog → reviewer · autonomy auto · next review 2026-11-09
  Why: founder ask, issue #4 (2026-10-31, @everfields): "Please append one line to HANDOFF.md at the repo root saying: 'Second pilot run: Claude opened this PR on its own.' Open a pull request yourself with the change and reference this issue." The `@claude` action committed 864e76d on `claude/issue-4-20261031-1349` but could not open the PR, so the ask sat unfinished for 6 days.
  Done when: a PR with exactly that one-line change, saying "Closes #4", is merged by the reviewer and issue #4 is closed.
  Status: in progress (run 2611062158-backlog-6725 put 864e76d on `cos/issue-4-handoff` and requested the PR with `cos pr open`)

## Next

## Later

- **B-003 North-star count should ignore runs with no tool calls** · size S · owner retro · autonomy auto (engine change goes upstream; the founder harvests it) · next review 2026-11-20
  Why: learnings 2026-11-04: run 2611040234 was recorded `ok` with no working shell. A ledger `ok` doesn't prove a healthy run.
  Done when: retro either records an upstream lesson (with the run evidence) that the clean-run count requires tool_calls > 0, or drops this item with a reason.
  Status: ready (retro's next weekly run)

## Waiting
On a gate, the COO, the founder or an outside party; each names what it waits for and until when.

- **B-002 Alarm #8: the incident loop has not succeeded for 67 h** · size S · owner incident · autonomy auto · next review 2026-11-09
  Why: alarm issue #8 (opened 2026-11-06 20:57 UTC by the pulse). Production safety ranks first, but the incident loop owns it.
  Done when: an incident run ends `ok` and #8 is closed with a cause and postmortem.
  Status: waiting on the incident run (agenda `2026-11-06-incident-new-alarms-8-8c3e`, then the daily 08:40 sweep). Deadline 2026-11-09: if #8 is still open at the next backlog run, escalate on the thread.

## Inbox
New items from any worker, untriaged.

## Done
Newest first, with the commit or PR and the date. Never deleted.
