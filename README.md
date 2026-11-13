# RentalInsights-Frontend
Frontend for RentalInsights

## Paid-report ad test (`/reports/`)

`reports/index.html` is the pre-order landing page for the ad test, served at
https://rentalinsights.ai/reports/.

- Market: `?m=memphis` or `?m=cleveland`. Price arm: visitors are split 50/50
  between $49 and $149 (force one with `?p=49` / `?p=149`).
- Edit the `CONFIG` block at the top: Stripe Payment Links (one per market and
  price), Meta Pixel / GA4 IDs, and each market's stats.
- Waitlist, survey and funnel events post to the app's `apps.preorders`
  endpoints (`https://app.rentalinsights.ai/api/landing/...`); payments are
  recorded by the Stripe webhook there. Results: `/reports/preorders/stats/`.
- Set each Payment Link's success URL to
  `https://rentalinsights.ai/reports/?paid=1&m=<market>&p=<price>`.
- Use only letters, digits and dashes in `utm_campaign` / `utm_content`.
