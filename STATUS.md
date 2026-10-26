# EasyMoney MRR: status (2026-10-25 ~21:25 ET)

## Live landings (all CTAs checked 200 at ~21:24 ET)
1. https://mattobie17.github.io/easymoney-mrr/  (GH Pages, owned by another worker): at ~21:24 ET still had raw Stripe Featured/Verified links; CEO corrected to /advertise/ at 21:23 and another worker is fixing that repo. Local public/index.html = advertise version.
2. https://easymoney-mrr-mpobrien1717-9829.vercel.app/  (Vercel, older multi-plan page): Featured/Verified -> canmyaiuse /advertise/ checkout
3. https://mattobie17.github.io/easymoney-cmau-ads/  (GH Pages, repo mattobie17/easymoney-cmau-ads, this worker): vendor squeeze, Featured/Verified -> /advertise/ checkout (auto-fulfilling), $1 kit secondary
- Vercel redeploy: 403 on team_8NOpp9vZ992gckLq6rIlChQ2 (scope mpobrien1717-9829), so not redeployed.

## Copy risk on landing 1 (until its fix lands)
Its Featured/Verified notes say "Paste your canmyaiuse server link... goes live automatically", but the raw Payment Links collect no server field and the webhook ignores them (see below). Either fix the copy ("we'll set up your placement after payment") or add a custom field + metadata to the links.

## Why NOT the raw Payment Links (bJe3... Featured / 5kQ3... Verified)
Checked via Stripe API: plink_1UUcUGH6wu2UiC186ocBbs1L (Featured) and plink_1UUcUFH6wu2UiC18ceL0XojT (Verified)
have metadata {sku, source:easymoney_mrr} only, NO custom fields, and redirect to /advertise/?paid=... which the site does not handle.
- canmyaiuse stripe-webhook ignores anything without metadata.site=canmyaiuse -> no placement is created.
- The buyer is never asked which server -> can't even fulfill by hand without emailing them.
To make raw links fulfill: add a custom_field (server link) + metadata site=canmyaiuse, and teach the webhook to create the order from a payment-link session (no pending:order_id exists). Until then /advertise/ is the only auto-fulfilling path.

## Stripe (acct_1URNPjH6wu2UiC18, live)
- 0 subscriptions / $0 at last check. No new products, prices or Payment Links created.

## Directory submissions: NOT done
Submitting listing forms is a public post under Matthew's name and wasn't explicitly approved. Candidates (free): IndieLineup, ListYourApp, Uneed, SaaSHub, BetaList, AlternativeTo; for canmyaiuse itself: mcp.so, glama.ai, PulseMCP.

## 2026-10-25 21:49 EDT — vendor squeeze conversion fix
- Removed 'downtime alerts' from Verified (replaced with 'Verified vendor label + badge upgrade').
- Removed mid-page $1 kit box; tiny footer link only.
- Featured $149/mo / Verified $49/mo CTAs → canmyaiuse.pages.dev/advertise/ only; no Payment Links, no Pro/Team.
