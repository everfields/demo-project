# What the market taught us, across the founder's companies

Real attempts with real numbers, newest first. The `improve` mode adds what each company writes under **Upstream** with the tag **market**. A lesson here is a fact about what happened, with where it came from. When it changes what the next company should do, it also goes into the method or a playbook.

## Survey of the first businesses (2026-11-06)

No current business shows real revenue in its files. The strongest real usage was a friends' pool and a 2024 website. In four of them, building ran far ahead of reaching people.

| Business | Pattern | Best traction | What it taught |
|---|---|---|---|
| IntelligencePick | Affiliate, AI product picks | 2024 site: ~400 visits a month, 125 Amazon clicks, ~$11 a month. Today: 1 click, ~1,880 impressions | Templated scale on a young domain gets demoted; the people who arrive do buy |
| AntiSearch | Consumer app, one-answer AI verdicts | ~180 TikTok clips, median ~250 views, 8 followers; X suspended | Automated posting makes views, not an audience |
| Bot for President | AI politician, civic software | 1,364 commits in 15 days; 2 X followers, 0 of 3 founders | Output is not reach |
| RoomRacer | Affiliate, 3D configurator | 219 impressions, 6 GA4 users | Networks refuse a site with no traffic |
| Rebates | Service, success fee | No win closed in six weeks; no stranger reached | A test that needs friends never ran because nobody asked them |
| Resi Porra (fantasy World Cup) | Community, friends' pool | 17 players paying 20 € | An existing group plus real stakes works, with no marketing at all |

### The lessons
1. **Output is not reach.** Bot for President shipped 1,364 commits between 2026-10-06 and 2026-10-20, and its own week 1 review ended: "Production is necessary and it is not the bottleneck: distribution is." Nothing in that week "borrowed anyone else's audience". Source: `bot-for-president/loop/reviews/2026-10-12.md`.
2. **Automated broadcast into an empty account builds nothing.** AntiSearch: about 180 clips, 8 followers. Bot for President: 33 X posts, 2 followers. Eighteen posts reached three impressions. Sources: `antisearch-automation` branch `publisher-state`, `metrics/summary.md`; `bot-for-president/state/metrics.json`.
3. **Warm and human is what has worked.** 17 people paid 20 € to join the pool because someone they knew asked them. Yet warm tests get written down and skipped: AntiSearch's 20-tester bar has an empty log, and Rebates' three friends were never all named. A warm test needs an owner and a date like anything else. Sources: `fantasy_fifa_2026/docs/decisions/0021`, `the_best/strategy/launch.md`, `rebates/BACKLOG.md`.
4. **Every person who writes must get an answer within a day.** Bot for President's 4 inbound mails went unanswered for lack of a mailbox in the cloud. It called that "the one that failed first". Source: `bot-for-president/loop/reviews/2026-10-12.md`.
5. **What waits on the founder misses the launch.** Report #18 at IntelligencePick waited while "no outreach" left nothing else; Bot for President's press releases lapsed unsent. Anything the launch depends on needs a route that does not wait on a person. Sources: `intelligence-ranking/docs/research/2026-11-06-google-drop-plan.md`, `bot-for-president/inbox/2026-10-13-cohort-a-review-founders-distribution.md`.
6. **Templated scale on a new domain gets judged fast.** 2024: ~96,000 URLs, then 20 to 2 users a day. 2026: 720 pages, demoted within a week. Source: `intelligence-ranking/docs/research/2026-11-06-google-drop-plan.md`.
7. **Early numbers are mostly bots.** IntelligencePick: 88 % desktop from 88 countries, 1 click. RoomRacer: 106 of its 199 clicks came from one crawler. 90,568 AI-bot requests brought 0 AI referrals. Crawling is not demand. Sources: `intelligence-ranking/docs/research/2026-11-06-google-drop-diagnosis.md`, `roomracer/docs/seo-review.md`, `intelligence-ranking/docs/ops/reports/2026-W45.md`.
8. **Networks and platforms refuse the unproven.** Impact and FlexOffers declined RoomRacer for lack of traffic; Amazon and two brands accepted it. Apply where a brand has a reason to say yes. Source: `roomracer/data/programs.json`.
9. **Automated accounts are fragile.** @antisearch_ai was suspended on 2026-10-09, and earlier X accounts were banned. An account is an asset with a ban risk. Source: `antisearch-automation/docs/ANTI_BAN.md`.
10. **Buyers convert, but the unit value decides the model.** 2024: 13 % of Amazon clicks converted, for ~$11 a month. Amazon pays about $20 on a $2,000 rig; brand programs pay $100–150. Do the arithmetic per customer before the first test. Sources: `intelligence-ranking/docs/manifest-v1.md`, `roomracer/docs/strategy.md`.
