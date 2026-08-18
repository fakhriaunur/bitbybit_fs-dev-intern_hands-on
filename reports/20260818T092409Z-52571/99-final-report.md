# Bitbybit Exploration — Final Report

## Executive summary

- Overall weighted score: **`76.6 / 100`**
- Confidence: **Medium**
- Run status: **`PARTIAL`**, all 13 scenarios attempted; completion was intentionally bounded before external or irreversible actions
- Strongest area: **Feature breadth and integrations**. AI Studio, support, CRM, commerce, bitLink, multiple WhatsApp channels, Shopify, Indonesian shipping, and Shopee import coverage form a coherent platform story.
- Largest friction: **Onboarding and compact mobile navigation**. At 390px, the authenticated header overlaps on every critical route checked; onboarding gates and plan states need clearer explanations.
- Highest-priority recommendation: **Fix the 390px authenticated header collision, then add a safe seeded demo state for inbox/CRM/Commerce workflow validation.**

## Scope and environment

| Field | Value |
|---|---|
| Account | Existing candidacy account only |
| Product boundary | Product-only; no external integrations or real-world side effects |
| Driver/browser | `droid-control / agent-browser 0.27.0 / HeadlessChrome 152.0.0.0` |
| Desktop UA | Retained while changing viewport |
| Viewports | `1440x900`, `1024x768`, `768x1024`, `390x844` |
| Run dates UTC | `2026-08-18 09:24–11:09 UTC` |

## What was explored

- Scenarios attempted/completed: `13 / 13`
- Automated status totals: `6 PASS`, `7 PARTIAL`, `0 FAIL`, `0 BLOCKED`
- Discretionary observations: `8` take-home hypotheses refined; two confirmed product-quality findings recorded
- Authenticated routes: `14` global destinations plus AI, CRM, bitLink, Commerce, settings, and docs sub-surfaces
- Blocked flows: none; OAuth, messaging, imports, orders, payments, publishing, upgrades, trials, and API-key creation were intentionally not entered

## Findings

### Worked well

- Global navigation reached 14 authenticated product routes with no captured page errors — evidence `NAV-01-S01`.
- AI Studio exposes agent, knowledge, tagging, AI Playground, channel, and skill concepts without requiring a publish — evidence `AI-01-S01`–`AI-01-S03`.
- Authenticated Integrations catalog clearly names WhatsApp modes, Shopify product integrations, Meta/social channels, payments, reviews, and Indonesian shipping — evidence `INT-01-S01`.
- Commerce includes Shopee Beta CSV/XLSX auto-detection and mapping, a useful regional-marketplace workaround — evidence `COM-01-S02`.
- Public docs cover product guides, setup, automation, customer data, API reference, and AI-readable endpoints — evidence `DOC-01-S01`–`DOC-01-S02`.

### Confusing or risky

- Onboarding exposes 20% progress, WhatsApp-not-connected state, locked commerce skills, and Skip/Continue controls, but no visible Continue transition was captured — evidence `ONB-01-S01`–`ONB-01-S03`.
- Customer Sync is present in Settings navigation but the captured destination renders only the settings shell — evidence `CRM-01-S04`–`CRM-01-S05`.
- Developer tools clearly require Standard or higher, with Export CSV and filters disabled; packaging/access rationale is not shown in context — evidence `INT-01-S02`.
- Empty inbox/orders/customer data prevented validation of handoff, customer context, and transaction workflows without crossing safety boundaries — evidence `CHAT-01-S01`–`CHAT-01-S06`, `CRM-01-S01`–`CRM-01-S05`, `COM-01-S01`.

### Performance and responsive behavior

- Public landing sample: TTFB `84.3ms`, FCP `384ms`, LCP `444ms`, CLS `0.04` — evidence `PUB-01-S08`.
- Authenticated samples: Home LCP `2756ms`, AI Studio `1664ms`, Integrations `1800ms`; CLS `0`–`0.04` — evidence `X-01-S02`.
- No horizontal overflow measured across public and authenticated viewport checks — evidence `PUB-01-S01`–`PUB-01-S04`, `X-01-S01`.
- At 390px, hamburger, bitbybit mark, and long account label overlap on Home, AI Studio, bitChat onboarding, and Integrations — evidence `X-01-S01`.
- At public 1024px, hero artwork overlaps supporting copy and part of the CTA row — evidence `PUB-01-S02`.

### Recommendations

- **P0:** Fix compact authenticated header layout at 390px — evidence `X-01-S01`.
- **P1:** Explain onboarding prerequisites/progress and provide safe seeded demo data — evidence `ONB-01-S01`–`ONB-01-S03`, `CHAT-01-S01`–`COM-01-S03`.
- **P1:** Repair Customer Sync destination and clarify permission boundaries — evidence `CRM-01-S04`–`CRM-01-S05`.
- **P2:** Document marketplace workarounds and plan/API gates — evidence `COM-01-S02`, `INT-01-S01`–`INT-01-S02`, `PLAN-01-S01`.

## Weighted evaluation

See `05-evaluation-matrix.md`.

| Criterion | Combined score | Weighted points |
|---|---:|---:|
| Workflow functionality and completion | `3.7 / 5` | `18.3` |
| Feature depth and usefulness | `4.1 / 5` | `16.5` |
| Integrations and interoperability | `3.9 / 5` | `15.8` |
| Performance and reliability | `4.0 / 5` | `11.9` |
| Onboarding, UX, accessibility, responsiveness | `3.5 / 5` | `7.0` |
| Pricing, limits, and product fit | `3.6 / 5` | `7.1` |
| **Total** | | **`76.6 / 100`** |

## Competitor benchmark

See `04-competitor-benchmark.md`.

- Primary layer conclusion: bitbybit has credible breadth against WhatsApp-first references, but runtime parity was not claimed.
- Secondary integration layer conclusion: Make, n8n, API2Cart, and SAAS Integrator are retained as an operating-model appendix, not direct substitutes.
- WhatsApp-first fallback used: WATI, respond.io, and SleekFlow, with Gorgias as adjacent ecommerce-support context.
- Comparability limitations: competitor pages are official public-source estimates; no competitor accounts or trial flows were used, and exact plan limits, reliability, and checkout/order behavior were not independently tested.

## Questions for interview

- Is onboarding goal selection intentionally single-select?
- Why does the captured Continue state not visibly advance?
- Is the text-box scroll/autoclose behavior known or expected?
- What is the roadmap for Shopee, Tokopedia, Lazada, Blibli, and other marketplace coverage?
- What should Customer Sync expose, and what permissions/data movement should users see?
- How are Developer/API, experimental, and student access programs gated?
- Which operator segment should define primary product-fit weighting?

## Evidence and limitations

See `00-index.md` for the evidence index.

- Credential values, cookies, tokens, and private customer data excluded: `YES`
- Temporary auth/session material removed: `YES`
- External actions avoided: `YES`
- Known limitations: no OAuth, messaging, uploads/imports, payments/orders, publishing, upgrades/trials, API keys, seeded support/customer/order data, full keyboard/focus audit, or competitor runtime testing.
