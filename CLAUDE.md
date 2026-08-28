# NEXTPredict 2027 — sponsorship brochure

Single-page React (Vite + Tailwind) app. Main content lives in `src/App.jsx`
(product/pricing data, ticket ladder, recognition tiers, calculator).

## Workflow

- Develop on branch `claude/2027-ticket-pricing-brochure-p79mqg`.
- Run `npm run build` to verify changes compile.
- Commit with a clear message and push the branch.
- `npm run deploy` (= `vite build && npx gh-pages -d dist`) publishes to
  gh-pages once Pages is enabled for this repo.
- Open a fresh PR into `main` only when asked.

## Notes

- Pricing/product data is the `pricing` array in `src/App.jsx`; each item has
  `bullets` (a `\n`-separated string) with `📅` slot/availability lines and
  `⚠️` condition notes (either/or routes, opt-in wording).
- The pricing array is the 2027 rate card from
  `NEXTPredict_2027_Commercial_Master.xlsx`, sheet `10_Olivia's_2027_Pricing`
  (canonical prices, reconciled 27 Aug 2026). Partnership prices are EUR;
  ticket prices are USD (sheet `04_Ticket_Pricing`).
- Internal-only content (revenue targets, discount caps, pipeline, 2026
  actuals, COS, open decisions) is deliberately excluded from the brochure.
- Exclusive/shared routes over the same inventory (NEXTworking evenings,
  Stage 2/3 per-day vs both-days, Nourish bars) are enforced as conflicts in
  the `CONFLICTS` map — never sold together, never double-counted.
- To mark a product sold or reserved, add one line to the `PRODUCT_STATUS`
  map in `src/App.jsx` (search "SALES DESK"), e.g.
  `'Leadership Stage Partner': 'sold',` — card badge, calculator button and
  rate-card PDF all react automatically.
- Recognition tiers: Silver <€30k, Gold €30–79,999, Platinum €80–134,999,
  Diamond ≥€135k by total spend; Headline is gated on the Headline Partner
  product, not spend.
- Venue/date lines say "October 2027 · New York City · exact dates and venue
  to be announced" — update them the moment Event Ops confirms.
- OPEN DECISION on the ticket ladder: `ticketLadder` uses the master's Early
  Bird prices (VIP $2,199 / Full $1,299 / Conference $949). The NEXT Commercial
  2027 plan carries a different set ($2,599 / $1,499 / $1,099); Standard and
  Late agree in both. The master's Early Bird sits 34–38% below the closing
  price against a portfolio benchmark band of 15–30%, so the recommendation to
  Stuart is to adopt the plan's Early Bird. If that is approved, update the
  three Early Bird prices and the two formula-linked rates that follow Full
  Event (Day Pass to $899 at 60%, Operator & Regulator to $750 at 50%).
- Hold/do-not-sell items (Gallery Projection Screens, Highline Hall Back
  Columns, Projection Mapped Millwork Wall, Wall Frame Around LED) and the
  unvalidated Awards concept are intentionally NOT in the brochure.
