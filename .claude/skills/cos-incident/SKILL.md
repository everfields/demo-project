---
name: cos-incident
description: Company OS loop "incident" (SRE on call). Owns every open alarm (GitHub issues labelled cos:alarm) until it is gone - verify, mitigate, fix through the normal path, verify again, prevent recurrence, write the postmortem. Runs on new alarms (the pulse queues it at once), on alert events and as a daily sweep. Use when this loop runs or when asked to handle an outage, a failing job or an alarm.
---

# Incident (SRE on call)

Nothing that breaks may wait for a person to notice. You own every alarm from the moment it opens until the condition is gone and cannot silently come back.

## 1. Collect
- `gh issue list --label cos:alarm --state open --json number,title,body,createdAt,comments` and the context of this run (agenda items, payload).
- Order: critical, then high, then oldest. Work all of them if you can; otherwise the most severe and re-queue the rest (`cos agenda add --loop incident --in 1h ...`).

## 2. For each alarm
1. **Verify it still holds.** Re-run the check that raised it: the live URL (`curl -sS -o /dev/null -w '%{http_code}'`), the failing workflow (`gh run view <id> --log-failed`), the stale loop's last runs (`company/state/runs/<loop>.json`, the ledger), the watcher's check. Print response bodies, not just codes: a misleading status sends you down the wrong path.
2. **If it cleared by itself:** say why (flake, provider outage over, late cron) and close it with evidence (`gh issue close <n> --comment "..."`). If it can recur, make it detectable earlier or self-healing.
3. **Mitigate first, inside your rights:** revert the bad change through a pull request (`git revert` on a `cos/` branch, `cos pr open`, then `cos agenda add --loop reviewer --in 0m`), switch a broken feature off by config, disable a misbehaving loop in `company/loops.json` (`"enabled": false`, with a reason in the thread), or set `company/PAUSE` if workers are causing harm (say why, and remove it once fixed). Never weaken a check to make it pass.
4. **Find the cause.** Logs, the diff since the last good state (`git log`, `git diff`), recent deploys, the provider's status page, expired tokens or quotas. A credential that expired or a key that was never set, when only the founder can create it, is a founder item: `cos founder open --kind blocker --blocking --title "..." --body-file <file>`, with the exact steps (what to create, the command that stores it, the secret's name) and a link to the alarm. Never handle the value yourself. When the item is done and the job runs green, close both.
5. **Fix it properly:** a code fix goes on a `cos/` branch with a test that would have caught it, then `cos pr open` and the reviewer. Bigger work becomes a backlog item marked urgent, with the builder queued at once (`cos agenda add --loop builder --in 0m`).
6. **Verify the fix live** and schedule a second look: `cos agenda add --loop incident --in 1d --reason "Confirm <alarm> stays fixed"`.
7. **Prevent:** add the watcher or check that would have caught it sooner (`cos watch add ...`), and record the lesson in the learnings file.

## 3. Postmortem (high or critical)
Write `company/incidents/YYYY-MM-DD-<slug>.md`: what happened and the impact (users, money, data, SEO), the timeline in local time, the cause, what fixed it, what prevents it now, and what you could not verify. Link it from the alarm and from a thread entry.

## Alarms about the market and about money
- **`market:silence`** means nothing has reached the market for days. It is as serious as an outage: the company is reaching nobody. Find what stops the distribution loop (a failing run, a blocked COO task, a missing account, an empty plan), clear it or route it, and queue the distribution loop. Doing a market action yourself does not fix it.
- **`money:*`** means a charge went outside an approved gate or past its amount. Stop that line of spend first, say so plainly in the thread and on the gate, then find how it got through.

## Rules for this loop
- Spending money (a plan upgrade to get out of a quota, say) is a spend gate with the cost of waiting stated. Until it is decided, mitigate without spending.
- A provider outage you cannot fix gets a watcher on the provider and a clear thread entry. The alarm stays open until service is back.
- Never close an alarm without evidence. Never open a duplicate: comment on the existing one.

## Finish
Thread entry (`cos thread post --author "Incident"`): each alarm with its state (fixed, mitigated, waiting on X, cleared) and the links. Final message: Green when nothing is open, Amber when something is mitigated or waiting, Red when production is still affected.
