# Discretionary Observations

Preserve source observations from `takehome.md` as observations. Confirmed findings below are limited to captured public or in-product evidence.

## Source observations from the take-home

These notes were extracted from the original take-home file. They remain hypotheses or product ideas unless the evidence below confirms them.

| Area | Source observation or suggestion | Question to investigate |
|---|---|---|
| Onboarding and stack | The interface appeared to use React and Next.js, which could support a mature SaaS ecosystem and LLM-assisted development. | Confirm technical assumptions separately from product behavior; do not treat visual inference as proof. |
| Onboarding behavior | An option text box might scroll or close unexpectedly when clicked or dragged. | Is this a repeatable usability defect or an expected interaction? |
| Onboarding goals | The current-goal control appeared to allow only one selection. | Should users select multiple goals, or is one primary goal intentional? |
| Pricing and promotion | Referral or promotional codes, pay-as-you-go pricing, or a-la-carte plans could reduce entry friction. | Which packaging models are planned or strategically supported? |
| Documentation and support | A knowledge base with docs and manuals could reduce reliance on chat-only support. | Which setup tasks should users complete independently? |
| bitLink branding | The bitbybit logo text may be intentional literal text rather than a missing rendered logo. | Is text-based branding intentional across products? |
| Marketplace coverage | Sophisticated scraping or alternative workflows could support marketplaces without explicit APIs, including Shopee, Tokopedia, Lazada, and Blibli. | Which marketplaces are supported natively, through imports, through APIs, or only on the roadmap? |
| Customer data | Google Contacts or WhatsApp Contacts integration could improve CRM setup. | Is contact sync in scope, and what permissions should it require? |
| Subscription and access | Experimental integrations or features, plus free access for developers, students, or selected businesses, could encourage adoption. Deposits or usage safeguards could protect fair use. | How should experimental and educational access be gated without encouraging abuse? |

## Observation matrix

| ID | Observation | Impact | Automated evidence | Hypothesis | Recommendation | Confidence | Status |
|---|---|---|---|---|---|---|---|
| `H-01` | Onboarding option text box scroll/autoclose may glitch | Could interrupt setup and reduce confidence | `ONB-01-S01`–`ONB-01-S03` | Repeatability still not proven; current flow exposed checklist and skill modal, not original text-box behavior | Run focused keyboard, scroll, and focus regression test with a disposable fixture | Low | `PARTIAL` |
| `H-02` | Current goal may need multi-select | Single-select may oversimplify diverse operator intent | `ONB-01-S01`–`ONB-01-S03` | Existing onboarding did not expose a clear goal selector in captured state | Label primary-goal semantics or support multi-select if multiple workflows are intended | Low | `PARTIAL` |
| `H-03` | Referral code and a-la-carte pricing may be useful | Could lower adoption friction for narrow product entry | `PUB-01-S09`, `PLAN-01-S01`, `LINK-01-S03` | Product-level tiers and Free entry are confirmed; referral, student, usage-based, and a-la-carte paths were not surfaced | Clarify product-by-product entry and promotion/access paths | Medium | `PARTIAL` |
| `H-04` | Docs/manuals may reduce chat-only support dependence | Self-service setup can reduce support load | `PUB-01-S11`, `DOC-01-S01`–`DOC-01-S02` | Confirmed: docs cover products, setup, automation, customer data, API, and AI-readable endpoints; one WhatsApp article defers core prerequisites to a linked guide | Link task docs from in-product gates and expand prerequisite checklists | High | `PASS` |
| `H-05` | Literal bitLink text may be intended branding | Ambiguous logo treatment can create perceived rendering defect | `LINK-01-S01`–`LINK-01-S03`, `X-01-S01`–`X-01-S03` | Authenticated bitLink uses editable brand-name text and preview iframe; no missing-logo defect confirmed. Mobile header text collision is a separate confirmed polish issue | Keep brand-name/text behavior explicit; fix compact-header collision | Medium | `PARTIAL` |
| `H-06` | Non-native marketplace integrations may need alternative workflows | Missing marketplace coverage may increase integration effort for regional merchants | `PUB-01-S10`, `INT-01-S01`, `COM-01-S02` | Shopee is not an authenticated connector card, but Commerce provides Shopee Beta CSV/XLSX auto-detection and mapping. Tokopedia, Lazada, and Blibli were not surfaced | Document marketplace import limitations and prioritize native connectors by demand | High | `PARTIAL` |
| `H-07` | Google/WhatsApp contact sync may improve CRM onboarding | Manual contact setup can slow CRM activation | `CRM-01-S01`–`CRM-01-S05`, `DOC-01-S01` | Customer filters/import history exist; Customer Sync menu loads no substantive controls in captured state. Direct contacts sync remains unconfirmed | Repair or clarify Customer Sync destination and show import permission boundaries | Medium | `PARTIAL` |
| `H-08` | Experimental access or developer/student programs may improve adoption | Early adopters need safe access to advanced capabilities | `INT-01-S02`, `PLAN-01-S01`, `LINK-01-S03` | Standard+ gate for Developer tools and product-level plans is confirmed; student/experimental access not surfaced | Explain gate rationale and publish safe access path if programs exist | High | `PARTIAL` |

## Confirmed discretionary notes

### Product narrative and breadth

- What was noticed: Public and authenticated surfaces consistently connect AI agents, shared support, CRM, commerce, link-in-bio, loyalty, and integrations.
- Where: Public landing, authenticated global navigation, AI Studio, bitChat, bitCRM, Commerce, bitLink.
- Why it matters: Strong breadth supports a unified-platform story, but empty states and cross-product plan gates can make the first usable workflow unclear.
- Evidence: `PUB-01-S01`–`PUB-01-S11`, `NAV-01-S01`, `AI-01-S01`–`AI-01-S03`, `CHAT-01-S01`–`CHAT-01-S06`, `CRM-01-S01`–`CRM-01-S05`, `COM-01-S01`–`COM-01-S03`.
- Confidence: Medium to High.

### Responsive header collision

- What was noticed: At 390px, hamburger, bitbybit mark, and long account label occupy the same header row and visually overlap on Home, AI Studio, bitChat onboarding, and Integrations.
- Where: Authenticated mobile viewport.
- Why it matters: Header identity and navigation become ambiguous even though content remains scrollable and no horizontal overflow occurs.
- Evidence: `X-01-S01`–`X-01-S03` and temporary screenshots named `X-01-*-390x844.png`.
- Confidence: High.
