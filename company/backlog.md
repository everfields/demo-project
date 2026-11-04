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

## Next

## Later

## Waiting
On a gate, the COO, the founder or an outside party; each names what it waits for and until when.

## Inbox
New items from any worker, untriaged.

## Done
Newest first, with the commit or PR and the date. Never deleted.
