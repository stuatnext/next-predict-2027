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
- The pricing array is the 2027 rate card from the NEXTPredict 2027
  commercial master (canonical prices, reconciled 27 Aug 2026). Partnership
  prices are EUR; ticket prices are USD.
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
- Design follows the NEXT.io house system shared with the New York and Valletta
  brochures: brand yellow #ffcf33 on brand dark #242426, Inter throughout, and
  the official NEXTPredict logo in `public/logos/`. Keep any new work on those
  tokens — no separate palette or display face for this event.
- Venue/date lines say "October 2027 · New York City · exact dates and venue
  to be announced" — update them the moment Event Ops confirms.
- DECIDED (Stuart, 31 Aug 2026): the ticket ladder uses the approved plan's
  Early Bird prices (VIP $2,599 / Full $1,499 / Conference $1,099), with the
  two formula-linked rates cascaded from Full Event (Day Pass $899 at 60%,
  Operator & Regulator $750 at 50%). Standard and Late are unchanged. The
  commercial master still carries the earlier Early Bird set — update it at
  the next master revision.
- DECIDED (Stuart, 3 Sep 2026, two rounds — Pierre's mandate: NEXTPredict
  prices at roughly double NYC 2026, which NEXTPredict 2026 already carried;
  NYC 2027 rose ~50% on 2026, so the mandate ≈ ×1.33 of the live 2027 NY
  card and the card's ×1.54 median exceeds it — do NOT double against 2027
  prices): comparison-driven repricing vs the New
  York card; every matched product now prices above its New York equivalent.
  Digital Event Guide €35k, Lanyard €45k per unit, Wi-Fi €28k, Stage 2 Per
  Day €65k / Both-Days €115k (11.5% two-route discount) / Presenter €55k,
  Stage 3 Both-Days €60k (fixes the zero premium vs 2× NY per-day and the
  27% two-route discount), Leadership Chair €45k, Day 1 NEXTworking shared
  €38k (5 slots; keeps the €150k exclusive at a 21% discount, within the
  ≤25% rule for 4+ slots), Exhibition 6x8 €135k / 8x4 €110k / 6x4 €75k /
  6x2 €60k (new product, two adjacent cluster positions, 6 max from the
  12-position pool) / 3x2 €33k (~+16–23% over NY turnkey; the 6x8 alone
  reaches the Diamond tier threshold). The Start-Up Zone (€9.5k/€16k) deliberately stays
  accessible and is not benchmarked against New York. The commercial master
  still carries the earlier set — update at the next master revision.
- A small set of held items and unvalidated concepts is intentionally NOT in
  the brochure; the list lives in the commercial master, not in this repo.
