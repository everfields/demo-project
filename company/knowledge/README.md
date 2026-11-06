# What we know across the companies

The shared memory of the founder's businesses. It lives in the `launch-company` skill and is copied into every company as `company/knowledge/` on each install and upgrade, so that the cloud workers can read it. Workers can't change their copy: `company/knowledge/**` is always protected.

| File | What it holds |
|---|---|
| `first-100.md` | The method for reaching the first customers. Every company follows it until it reaches its first target. |
| `rules-of-the-road.md` | The law and each channel's rules: what an unattended agent must do and must never do. |
| `market-learnings.md` | What the market actually did to the founder's companies, with the numbers. |
| `playbooks/` | One file per business pattern: the route, the tests, the bars and the decisions. `generic.md` when nothing else fits. |

## How it grows
1. A company learns something in the market. Its workers write it in `company/learnings.md`, under **Market learnings**, and under **Upstream** with the tag **market** if another company could use it.
2. On Sundays, `company-os-improve` runs `/launch-company improve`. It harvests those lessons into `market-learnings.md`, and into the method or a playbook when they change what the next company should do. A pattern seen in a second company gets its own playbook.
3. `upgrade` sends the new knowledge to every company.

So the second e-commerce test starts where the first one ended.

## Rules for this folder
- Facts with sources and dates. An example is labelled as one, and a number with no source is left out.
- A benchmark goes stale: prefer a formula the worker can compute for its own business, and re-check anything older than a month before relying on it.
- Keep each file short enough for a worker to read in one go. Add what changes a decision; drop what doesn't.
