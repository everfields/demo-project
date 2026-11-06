# Assets

What the company owns or uses to operate: identities, domains, accounts, keys, and where each secret lives. **Names and places only, never a secret value.** The COO desk keeps this file true. Every loop reads it before asking the founder for anything.

Status: `planned` (decided, not provisioned yet) · `live` · `waiting` (on a COO task or a founder item: link it) · `retired`.

## Identities
The names the company acts under: its contact address, the identity its accounts are signed up with, and who acts for it (the founder, the COO, the workers).

| Identity | What for | How it works | Status | Notes |
|---|---|---|---|---|

## Domains and DNS
| Domain | Registrar (account) | DNS host | Renews | Status |
|---|---|---|---|---|

## Accounts
Every outside service. "Login" says whose login it is: the founder, the company identity or the COO. "Plan" says free or paid; paid needs an approved spend gate, so link it.

| Service | What for | Login | Plan | 2FA held by | Status |
|---|---|---|---|---|---|

## Keys and secrets (names only)
| Name | What it unlocks | Stored in | Read by | Expires | How to renew |
|---|---|---|---|---|---|
| `CLAUDE_CODE_OAUTH_TOKEN` | the workers' Claude subscription | repository secret or the runner's vault | the loop runner | one year after `claude setup-token` | the founder runs `claude setup-token`, then stores it the same way |

## Decisions
What the company decided it needs and why, what it decided not to have and why (for example: no mailbox, because a forward on the domain is enough), and what is still being provisioned, with links.
