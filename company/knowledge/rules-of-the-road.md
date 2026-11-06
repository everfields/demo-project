# Rules of the road

What an unattended agent must do and must never do in the market. Checked 2026-11-06. These are facts for guardrails, not legal advice, and the company's founder is established in Spain, so Spanish and EU law apply first. Re-check anything older than a month. When a rule here and a target collide, the rule wins. Where it says "founder gate", open one.

## Who may act where

| Channel | Unattended | Never |
|---|---|---|
| Own site, own pages | Yes | |
| Bluesky | Yes, by API ([5,000 points/hour, a post costs 3](https://docs.bsky.app/docs/advanced-guides/rate-limits)) | Undisclosed ads, fake accounts ([rules](https://bsky.social/about/support/community-guidelines)) |
| Mastodon | Yes, by API, within each server's rules | |
| X | By API only: [$0.015 a post, $0.20 with a URL](https://docs.x.com/x-api/getting-started/pricing.md) (spend), labelled Automated | [Browser automation means permanent suspension](https://docs.x.com/developer-guidelines). No unsolicited DMs or mentions. Replies only when summoned |
| Instagram | By API, [professional accounts](https://developers.facebook.com/docs/instagram-platform/content-publishing) | Automated account creation |
| LinkedIn | [Member posts by API](https://learn.microsoft.com/en-us/linkedin/consumer/integrations/self-serve/share-on-linkedin). Pages need reviewed access | [Bots for messages, likes, invites or contacts](https://www.linkedin.com/legal/user-agreement) |
| TikTok | [Private-only until the API client is audited](https://developers.tiktok.com/doc/content-posting-api-get-started); label AI content | [Automation tools](https://www.tiktok.com/community-guidelines/en/integrity-authenticity) |
| Reddit | No: [API requests closed 2026-10-31](https://www.redditapis.com/blogs/reddit-data-api-october-31-cutoff-2026) (secondary source). A person only | [Automated unprompted DMs](https://support.reddithelp.com/hc/en-us/articles/360043512931-Don-t-break-the-site), [heavy self-links](https://support.reddithelp.com/hc/en-us/articles/360043504051-Spam) |
| Hacker News | No. A person, who also writes the text | ["Please don't automate posting"; no generated or AI-edited text](https://news.ycombinator.com/newsguidelines.html). No landing pages in [Show HN](https://news.ycombinator.com/showhn.html) |
| Product Hunt | No. A person, who also writes the text | ["No LLMs or Chrome extensions"](https://help.producthunt.com/en/articles/10030102-commenting-guidelines), [company accounts, asking for upvotes](https://www.producthunt.com/launch) |
| Facebook groups | No. [No API since 2024](https://developers.facebook.com/docs/graph-api/changelog/version19.0/). A person; admins decide | Automated collection, a second personal account |
| Directories, marketplaces, forms | The COO, within each site's terms | Amazon requires agents to [identify themselves and bars imitating humans or solving CAPTCHAs](https://affiliate-program.amazon.com/help/operating/policies) |

**On every network:** no sock puppets, no identical cross-posts, no buying engagement, and never a replacement account after a ban. A ban goes to the founder.

## Outreach law
- **Spain:** [LSSI art. 21](https://www.boe.es/buscar/act.php?id=BOE-A-2002-13758) bans promotional email or equivalent electronic messages without prior request or express authorisation. The one exception is existing customers, for similar own products, with opt-out. Art. 20 bans hiding the sender. Fines reach €30,000, and €150,000 for mass or insistent sending; real cases have been smaller ([€1,000](https://www.aepd.es/documento/ps-00136-2021.pdf)).
- **A business address does not help:** the AEPD [sanctions it for legal persons and generic addresses too](https://www.aepd.es/documento/ps-00559-2021.pdf).
- **EU:** [Germany](https://www.gesetze-im-internet.de/uwg_2004/__7.html) needs prior consent, businesses included. [France](https://www.cnil.fr/fr/la-prospection-commerciale-par-courrier-electronique) allows professionals on legitimate interest if it fits their job.
- **US:** [CAN-SPAM](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business) needs no prior consent, but LSSI binds Spain-established senders with no carve-out for the recipient's country, so it may not protect this founder. Treat DMs as email.

**So:** no promotional email or DM without a logged legal basis per recipient. Never a scraped or bought list. Every message names the sender and offers an opt-out, and an opt-out is final. US cold email is a founder gate. A message a person writes and sends one to one is the founder's or helper's own responsibility: give them this section.

## An agent must say it is one
[EU AI Act art. 50](https://digital-strategy.ec.europa.eu/en/faqs/transparency-obligations-under-article-50-ai-act) has applied since 2026-08-02. The [Commission's guidelines](https://ai-act-service-desk.ec.europa.eu/sites/default/files/2026-07/guidelines_on_the_implementation_of_the_transparency_obligations_for_certain_ai_systems_under_article_50_of_the_ai_act_bzptwqhk0ikg1dtlddap41psfy_131215.pdf) (non-binding) say agents that manage correspondence must disclose their artificial nature and whom they act for. Out of scope only if a human really reviews and sends. California [bars misleading bots used to sell](https://california.public.law/codes/ca_bus_and_prof_code_section_17941).

**So:** the first line of any autonomous email, DM or chat says "AI agent acting for <company>". Never deny being an AI. Show real product photos: an AI image that flatters the product is a listed deep fake.

## Fake proof
[EU UCPD Annex I](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:02005L0029-20220528) blacklists false reviews, claiming real customers without checks, false limited-time claims and posing as a consumer. Fines in coordinated cases reach at least 4 % of turnover or €2M. In Spain a prior price means the [lowest in 30 days](https://www.boe.es/buscar/act.php?id=BOE-A-1996-1072). The [FTC rule](https://www.ftc.gov/news-events/news/press-releases/2024/08/federal-trade-commission-announces-final-rule-banning-fake-reviews-testimonials) bans AI-generated reviews, undisclosed insiders and bought followers, and [fake countdown timers](https://www.ftc.gov/news-events/news/press-releases/2022/09/ftc-report-shows-rise-sophisticated-dark-patterns-designed-trick-trap-consumers) are a named dark pattern.

**So:** never write a review, a testimonial, a user count or an "as a customer" comment. Timers and stock claims need stored evidence. Company posts disclose the connection in the post itself.

## Selling what doesn't exist yet
Legal with conditions. [UCPD point 5](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:02005L0029-20220528) bans a price that hides reasons you can't supply. Spain expects delivery [within 30 days](https://www.boe.es/buscar/act.php?id=BOE-A-2007-20555) unless agreed. The [FTC order rule](https://www.ftc.gov/business-guidance/resources/business-guide-ftcs-mail-internet-or-telephone-order-merchandise-rule) needs a reasonable basis to ship. [Stripe prohibits](https://stripe.com/en-es/legal/restricted-businesses) charging where nothing is sold in good faith.

**So:** a fake door says "not available yet, join the list" before any card data. Never take money without a confirmed supplier and a stated date. Charge at shipment.

## Selling physical goods (Spain and EU)
- **Who may sell:** no real order until the founder confirms the registration and the legal notice is live. Habitual personal activity means [RETA](https://www.boe.es/buscar/doc.php?id=BOE-A-2015-11724), which is a founder step. Habituality decides, not an income floor; sources conflict, so check with a gestor.
- **Product safety:** [GPSR](https://eur-lex.europa.eu/eli/reg/2023/988/oj/eng), since 2024-12-13. No sale without an EU-established responsible operator (art. 16). Listings show the manufacturer, the responsible person, a picture, identifiers and warnings (art. 19). A Spanish dropshipper selling a non-EU product is [probably the importer](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A52021XC0323%2801%29) (inference). Own branding makes you the manufacturer (art. 13): that is a founder gate. Stop the sale and alert on any safety complaint.
- **Customs:** the €150 relief ended 2026-07-01 ([Reg. 2026/382](https://eur-lex.europa.eu/eli/reg/2026/382/oj/eng)). €3 per item until 2028-07-01, plus a [€2 fee since 2026-11-01](https://taxation-customs.ec.europa.eu/customs/eu-customs-reform_en) on distance sales. Item means same tariff class, description and origin. The US [suspended de minimis](https://www.cbp.gov/trade/basic-import-export/e-commerce/faqs) for all origins.
- **VAT:** [IOSS](https://sede.agenciatributaria.gob.es/Sede/iva/iva-comercio-electronico/cuestiones-generales.html) up to €150, OSS for intra-EU sales, home VAT [below €10,000](https://vat-one-stop-shop.ec.europa.eu/document/download/a316a98a-3b2b-4991-a9c0-3b5905d369fc_en?filename=OSS_guidelines_en.pdf).
- **Consumer rights** ([TRLGDCU](https://www.boe.es/buscar/act.php?id=BOE-A-2007-20555)): 14 days to withdraw from delivery, 12 more months if not informed. Refund within 14 days, including standard delivery. The consumer pays the return only if told. The button reads "pedido con obligación de pago". Build the [withdrawal function](https://eur-lex.europa.eu/eli/dir/2023/2673/oj/eng) anyway.
- **The site** ([LSSI art. 10](https://www.boe.es/buscar/act.php?id=BOE-A-2002-13758)): name, address, email, registry data, NIF, prices with tax and shipping. Acknowledge orders within 24 hours.

**So:** price the landed cost per item. Never undervalue, split or misdescribe a parcel. Show import charges before payment. Refunds are automatic, never argued.

## Paid ads
- **Meta:** [non-delivery, misleading pricing and refund violations](https://transparency.meta.com/policies/community-standards/prohibited-commercial-practices/) are prohibited, and [penalties reach linked users and pages](https://transparency.meta.com/policies/other-policies/our-prohibited-commercial-practices-policy/). There is no written dropshipping ban. Hidden shipping times and new-account spend spikes are the reported triggers (secondary source). The [Ads MCP](https://developers.facebook.com/documentation/ads-commerce/ads-ai-connectors/ads-mcp-server/ads-mcp-server-overview) creates and edits campaigns.
- **Google:** [hiding the ship-from location and unfulfillable listings are misrepresentation](https://support.google.com/merchants/answer/6150127?hl=en). [A new account after a suspension](https://support.google.com/adspolicy/answer/15938075?hl=en) is circumvention.
- **TikTok:** [missed delivery promises and slow support](https://ads.tiktok.com/help/article/tiktok-after-conversion-experience-policy?lang=en) get ads rejected and accounts suspended.

**So:** state the real ship-from and delivery time in the ad and on the page. Use a real address. Budgets are capped by a founder gate. Start small and ramp slowly on a new account.

## Email
[Resend](https://resend.com/legal/acceptable-use), [Postmark](https://postmarkapp.com/terms-of-service), [SendGrid](https://support.sendgrid.com/hc/en-us/articles/4404315959835-Email-Opt-in-and-Opt-out-Requirements) and [SES](https://aws.amazon.com/aup/) all forbid cold or unsolicited mail. Cold tools ([Instantly](https://instantly.ai/terms), [lemlist](https://www.lemlist.com/legal/terms)) leave compliance to you, and their terms do not make a send lawful. [Google Workspace](https://workspace.google.com/terms/use_policy/) bans unsolicited bulk mail. [Gmail](https://support.google.com/a/answer/81126?hl=en) needs SPF or DKIM, spam under 0.10 %, never 0.30 %.

**So:** transactional accounts only for mail people asked for. Halt at the provider's thresholds. Keep marketing and transactional domains apart.

## What the agents can really do
- **Grok Bot** ([docs](https://docs.x.ai/grok-bot/computer-and-apps)): routines cannot send email unattended; mail from the Bot's address [always waits as a draft](https://docs.x.ai/grok-bot/chat-and-collaboration). No posting feature is documented. Sign-ups need an OK, and CAPTCHAs, SSO, passkeys and card checks go to a human. Approval cards from background work [expire after 30 minutes](https://docs.x.ai/grok-bot/approvals-security-and-privacy), and the action does not run. A Vault card fills at checkout without approval, so never save one.
- **Claude scheduled tasks with Gmail:** the docs conflict, [ask rules stop a run](https://code.claude.com/docs/en/routines), and Anthropic [advises against](https://support.claude.com/en/articles/13364135-use-claude-cowork-safely) scheduling tasks that send messages. Treat as drafts until tested on the founder's own inbox.
- **Usage policy:** no [multiple accounts to evade safeguards, no coordinated inauthentic behaviour](https://support.claude.com/en/articles/12005017-using-agents-according-to-our-usage-policy).

## Not verified
Sources blocked: redditinc.com, reddit.com, x.ai's changelog, help.x.com and Meta's pages (snippets only). The AI Act reading rests on non-binding guidance. Spanish GPSR fines, packaging rules and the status of the withdrawal function need a lawyer.
