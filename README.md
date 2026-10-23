# FLIGHTFINDER ✈

## GitHub Pages website + Supabase Edge Function

The frontend is a static website. It invokes the deployed Supabase function at:
`https://xocizxszrqiexfxculsa.supabase.co/functions/v1/flightfinder-search`

### One required secret
In Supabase Dashboard → Edge Functions → Secrets, add:
- Name: `DUFFEL_ACCESS_TOKEN`
- Value: your Duffel API token

Use a live-mode token/account for real purchasable fares. Test-mode results are not real purchasable fares. Do not put the token in this repository.

### Deploy website
GitHub Actions publishes the static site to GitHub Pages after pushes to `main`. In GitHub repository Settings → Pages, choose GitHub Actions as the source if prompted. Website URL will be `https://anirudhadebbarma031214-commits.github.io/FLIGHTFINDER/`.

### Important
- Actual fares only appear after Duffel credentials and supplier access are configured.
- The browser re-searches every 10 minutes while this tab stays open and visible.
- Official airline links are carrier homepage handoffs, not guaranteed deep links to the exact itinerary. Always verify fare, baggage and availability before buying.
- Supabase function `flightfinder-search` has already been deployed separately. Its source should also be kept in `supabase/functions/flightfinder-search/index.ts` for version control.
