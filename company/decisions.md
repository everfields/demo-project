# Demo Co: decision log

Every decision that matters, newest first: the ones workers take inside their rights, and the founder's gates once decided. A decision with an uncertain effect names its review date, and a review entry closes it (kept, changed or reverted, with the numbers).

Format:

```
## D-001 · YYYY-MM-DD · <title>
- Decided by: <loop> (autonomous) | founder (gate #N, their words quoted)
- Context and evidence:
- Options considered:
- Decision and why:
- Success looks like (set before acting): metric, threshold, window
- Review: YYYY-MM-DD (agenda id)
- Outcome (added at review):
```

## D-001 · 2026-11-06 · The distribution loop stays enabled in the paused sandbox
- Decided by: retro (autonomous)
- Context and evidence: distribution run 2611062158-distribution-1147 asked retro to disable it: there is no market (charter: sandbox; plan.md: "This company must contact nobody"), and left on, it would raise a market-silence alarm around 2026-11-11. Two minutes later the founder's session set `company/PAUSE` again (00dfda7, "its workers stay off") and added the distribution agenda item "Sandbox: look again once the company is unpaused" for 2026-11-13.
- Options considered: (a) `enabled: false` in loops.json; (b) no change.
- Decision and why: (b). PAUSE already holds every non-critical loop. `marketSentinel` closes the silence alarm while paused, and the pulse workflow is off. Disabling the loop would also skip the item the founder set for its resume, and would make a future manual live proof report "loop disabled".
- Success looks like: no market-silence alarm and no distribution run while PAUSE is set.
- Review: at the first retro after a resume (retro is held while paused; nothing to measure until then).
- Outcome (added at review):
