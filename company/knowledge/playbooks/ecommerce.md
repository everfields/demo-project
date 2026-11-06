# Playbook: e-commerce, from a dropshipping test to an own store

A product is a bet. Test demand cheaply, sell real units on a proven product, then decide on stock, brand and store. "Try this product" on a company that already runs this line is a new bet, not a new company.

Checked 2026-11-06. [F] is a formula, [R] a vendor's or practitioner's rule of thumb, not a law. The law is in `../rules-of-the-road.md`, "Selling physical goods".

**`market.unit`:** orders from strangers. **Target:** 100 for the line; each bet has its own bar.

## Do the arithmetic before anything else [F]
Per unit, in the buyer's country:
- **Landed cost** = product + shipping + import cost + payment fee + pick-and-pack. Goods from outside the EU now add [€3 per item plus a €2 fee](https://taxation-customs.ec.europa.eu/customs/eu-customs-reform_en), which is 12.5 % of a €40 order. Add expected returns.
- **Contribution** = price without VAT − landed cost. That is your **break-even CPA**.
- **Break-even ROAS** = 1 ÷ margin ([Shopify](https://www.shopify.com/my/blog/break-even-roas-calculator)).
- **Maximum CPC** = contribution × conversion rate.
- **Minimum order value** = expected CPA ÷ margin.

For scale, Meta's e-commerce medians were CPM $16.80, CTR 1.93 %, CPC $0.87, CVR 2.7 %, CPA $32 ([1,247 accounts, 2026-10](https://www.webtonic.io/blog/e-commerce-facebook-ads-statistics)). At a 40 % margin, that needs an order value of about $80–95. A product that can't reach it through paid ads needs a free channel or a higher price. Kill it on paper rather than in the market.

## The route

| Stage | The question | What happens | Bar to move on |
|---|---|---|---|
| idea | Is this product worth a test? | Product and competitor research, the arithmetic, a legal screen, a supplier with EU stock if there is one | Contribution covers a realistic CPA, and no legal blocker |
| validation | Will strangers want it? | A one-product page, an honest waitlist or "not available yet", and a small ad test | Pre-registered intent bar, from the arithmetic |
| mvp | Will they pay, and can we deliver? | Real orders on a small batch, after the founder's legal steps | 8+ real orders with CPA under break-even [R] |
| launch | Can we reach 100 orders repeatably? | One channel, then a second; delivery, returns and support by the book | 100 orders, CPA known, returns and disputes under control |
| growth | Own stock and brand? | The decision below | The charter's targets |

## The smoke test (validation)
Costs little, needs no legal entity, and takes no money from anyone.
1. A one-product page with real photos, a real description and a price. The button leads to "not available yet: tell me when it is", said before any card data.
2. An ad test inside an envelope: 3–5 creative concepts, one ad set each ([R](https://scigrowth.com/blogs/strategy-growth-1/meta-ads-creative-testing-framework-dtc-2026-2)), showing real ship-from and delivery times. Five creatives give about 18 % odds of a winner ([~4–5 % win](https://library.motionapp.com/research/creative-benchmarks-2026/)), so never judge a product on one creative.
3. Read the steps in order (`../first-100.md`, "Dead channel, or badly run?"). Low CTR blames the creative, good CTR with no intent blames the page or the product.

## The real-order test (mvp)
Needs the founder's legal steps first: registration, the legal notice, a responsible person for the product. See the checklist. Then, per one vendor's rule of thumb, [scale these dollars to your break-even CPA](https://www.trygodmode.com/blog/when-to-kill-dropshipping-test-2026) [R]:
- no add-to-cart by $30–50: kill;
- no sale by $100–150: kill;
- at $150–300: CVR above 1.5 % with a healthy CPC doubles the budget, below 1 % kills;
- 8–15 conversions before committing more;
- **winner:** CPA under break-even at 8+ conversions;
- **dead:** CTR under 0.7 % across three distinct angles, and CVR under 1 % on a rebuilt page with healthy clicks.

By formula, 3 × break-even CPA with zero sales is a 95 % answer.

## Decisions along the way
- **Shopify or not:** default to Shopify for real orders. It costs [3 days free, then €1 a month for 3 months, then €32](https://www.shopify.com/es/precios) (€24 on annual), cards from 2.1 % + €0.30, [Shopify Payments works in Spain](https://help.shopify.com/en/manual/payments/shopify-payments/supported-countries), and the [Admin API](https://shopify.dev/docs/api/admin-graphql) lets an agent run the store. Software is cheap, but a custom store also means building the withdrawal function, legal pages, tax and dispute handling. A custom store with Stripe ([1.5 % + €0.25](https://stripe.com/es/pricing)) makes sense only when volume makes the fee difference pay for that. The smoke test needs neither. A human completes the sign-up, KYC and terms; the agent operates through the API, never a browser.
- **Which supplier:** prefer stock already in the EU, which avoids customs and may give you an EU responsible person. Confirm stock and delivery time in writing before the first order. Stripe [may ask for supplier orders or tracking](https://support.stripe.com/questions/received-a-request-to-upload-additional-business-information).
- **Own stock:** no rigorous threshold exists. Vendors say [30+ days of steady daily sales, returns under 3 %, roughly 500–1,000 monthly orders](https://fulfillmen.com/dropshipping-vs-3pl/) [R]. The formula [F]: move when margin gain × 90-day forecast units exceeds the cash at risk in the minimum order. It is a spend gate.
- **Own brand:** selling under your own name [makes you the manufacturer](https://eur-lex.europa.eu/eli/reg/2023/988/oj/eng). It is a strategy gate.
- **What to fix when carts die:** [extra costs 40 %, slow delivery 20 %, card trust 19 %, returns 13 %](https://baymard.com/lists/cart-abandonment-rate) of abandonments.

## Other channels to test
- **Creators:** TikTok Shop has about [21,000 local sellers in Spain](https://ecommercenews.eu/one-in-five-spanish-ecommerce-sellers-on-tiktok-shop/), and its affiliates are an estimated large share of revenue.
- **Marketplaces** where the product is already searched for.
- **Short video on real product use.** Shorts reach small accounts best (`../first-100.md`).

## The founder's checklist (once per legal entity, prepared to the last click)
1. Registration: autónomo or SL, with a gestor's check. A founder item before the first real order.
2. Legal notice, conditions, withdrawal form and privacy page, with the real NIF and address.
3. IOSS or OSS if the goods need it.
4. Shopify sign-up, KYC and payments; the ad account and its payment method.
5. The first envelope, by spend gate.

## After each bet
Write what happened under **Market learnings**, with the numbers: product, CPA, CTR, CVR, verdict. The next bet starts from there.
