# Automated Exploration

## Execution summary

- Runner: `droid-control / agent-browser`
- Start/end UTC: `2026-08-18 09:24–11:09 UTC`
- Scenarios attempted: `13`
- Scenarios completed: `13`
- Status totals: `6 PASS`, `7 PARTIAL`, `0 FAIL`, `0 BLOCKED`
- Recovery notes: Misc route exceeded a network-idle wait; fixed-delay recovery loaded it and Settings successfully.

## Scenario results

| ID | Status | Route(s) | Viewport(s) | Actual result | Side-effect class | Evidence IDs | Follow-up |
|---|---|---|---|---|---|---|---|
| `PUB-01` | `PASS` | `/`, `/pricing/`, `/integrations/`, `knowledge.bitbybit.studio/` | Four public viewports | Positioning, pricing, integrations, docs, diagnostics, and responsive behavior captured. | Read-only | `PUB-01-S01`–`PUB-01-S11` | Fix 1024px hero overlap. |
| `AUTH-01` | `PASS` | Login, `/home` | `1440x900` | Existing candidacy account logged in; baseline reached; promotional modal dismissed without account change; no page errors. | Account access, read-only | `AUTH-01-S01`–`AUTH-01-S02` | Keep auth evidence temporary-only. |
| `ONB-01` | `PARTIAL` | `/bitchat/onboarding` | `1440x900`, `390x844` | Existing workspace shows onboarding progress, WhatsApp-not-connected state, integration-dependent locked commerce skills, Skip/Continue controls, and 20% progress in the current state. No new workspace or selection was submitted. Continue did not produce a visible state change in the captured state. | Read-only; no new workspace | `ONB-01-S01`–`ONB-01-S03` | Clarify progress semantics and test goal-control behavior with a disposable QA fixture. |
| `NAV-01` | `PASS` | 14 global routes | Desktop baseline | Home, AI Studio, bitChat, bitCRM, bitApp, bitLink, bitLogin, bitLoyalty, Commerce, Analytics, Customers, Integrations, Misc, and Settings loaded with stable route metadata and no captured page errors. | Read-only | `NAV-01-S01` | Add route-level loading/error instrumentation in product QA. |
| `AI-01` | `PASS` | `/ai-studio/ai-agent`, `/knowledge-base`, `/ai-tagging` | Desktop baseline | Active Professional Assistant, live-chat-widget channel, knowledge upload/Add URL/Add text controls, and language/priority/intention tagging surfaces were discoverable. Publish/create actions were not used. | Read-only | `AI-01-S01`–`AI-01-S03` | Validate draft/test/publish guardrails with a safe fixture. |
| `CHAT-01` | `PARTIAL` | Livechat, Ticket, Quick replies, Chatbot, WhatsApp form, Chat widget | Desktop baseline | Inbox exposes channel tabs, search, filters, assignment buckets, and Connect Channel. Ticket search/date controls, chatbot templates/flows, form creation, and widget settings were visible. Inbox had no seeded conversation, so handoff/context behavior was not testable. | Read-only; no outbound communication | `CHAT-01-S01`–`CHAT-01-S06` | Add safe seeded conversation or product demo state for support-flow validation. |
| `CRM-01` | `PARTIAL` | Customers, Segments, Import history, Customer Sync | Desktop baseline | Customer search/source/tag filters, segment creation, import-history filters, and customer-sync navigation were visible. No customer import or sync was run. Customer Sync query loaded the settings shell without substantive controls. | Read-only; no contact transfer | `CRM-01-S01`–`CRM-01-S05` | Explain empty-state/import path and render or remove the Customer Sync destination. |
| `LINK-01` | `PARTIAL` | bitLink Links, Appearance, Social media, Subscription | Desktop baseline | Preview iframe, brand name/title/image/font controls, social toggles, Shopify connect CTA, analytics link, and Free/Starter/Growth/Pro Bundle pricing were visible. No public link was created or published; preview-after-edit was not tested. | Read-only; draft/publish boundary respected | `LINK-01-S01`–`LINK-01-S03` | Test draft preview updates with a reversible local value. |
| `COM-01` | `PARTIAL` | Commerce Orders, Products, Vouchers | Desktop baseline | Orders and vouchers were empty but had search/filter/add controls. Products exposed CSV upload, Shopify, Add individually, and `Shopee Beta` auto-detected/mapped CSV/XLSX import with instructions. Upload/import was intentionally not performed; cart/payment behavior was not reachable safely. | Read-only; no import/order/payment | `COM-01-S01`–`COM-01-S03` | Add a non-persistent sample catalog and make marketplace coverage explicit. |
| `INT-01` | `PASS` | Integrations, Settings → Developer | Desktop baseline | Authenticated catalog names Shopify product integrations, WhatsApp Business App/Cloud API/Sandbox, Instagram, Facebook, TikTok Beta, reviews, payments, Meta, and Indonesian shipping. Developer tools clearly require Standard+; Export CSV and filters were disabled. No Connect/OAuth action was used. | Read-only; no authorization | `INT-01-S01`–`INT-01-S02` | Link plan prerequisites and setup docs directly from each connector. |
| `PLAN-01` | `PARTIAL` | Settings → Plan management, bitLink Subscription | Desktop baseline | Plan management shows 100 AI Responses, top-up, disabled auto-charge, usage history, Free bitChat plan with no renewal, and no plan yet for several products. bitLink exposes product-level $0/$6/$19/$299 tiers and API/webhooks under Developer. Referral, student, and a-la-carte paths were not surfaced. | Read-only; no upgrade/top-up | `PLAN-01-S01`, `LINK-01-S03`, `INT-01-S02` | Explain cross-product plan state and gate rationale. |
| `DOC-01` | `PASS` | `knowledge.bitbybit.studio/`, `/bitcrm/connect-whatsapp-cloud-api` | Public | Docs index covers product guides, setup, campaigns, automations, triggers, customer data, API, and AI-readable endpoints. WhatsApp Cloud API article gives purpose and links to a full guide naming Meta verification, phone setup, and payment prerequisites. | Read-only | `DOC-01-S01`–`DOC-01-S02` | Expand prerequisite/checklist content in setup article. |
| `X-01` | `PARTIAL` | Home, AI Studio, bitChat onboarding, Integrations | Four viewports; desktop UA | No horizontal overflow across 16 authenticated route/viewport checks. At 390px, hamburger, bitbybit mark, and long account label overlap on all four routes; body controls remain reachable. Auth vitals and navigation timings were captured. | Read-only | `X-01-S01`–`X-01-S03` | Fix compact-header layout, then repeat screenshots and focus checks. |

## Detailed results

### `PUB-01` — Public landing, claims, navigation, and responsive layout

- Status: `PASS`
- Preconditions: Public browser session; no authentication.
- Steps: Open landing page; capture desktop and narrow viewport states; inspect public pricing, integrations, and docs; collect diagnostics and vitals.
- Actual result: Landing positions bitbybit as one AI platform for support, marketing, and commerce. Public navigation exposes products, solutions, Shopify, pricing, resources, sign-in, and get-started paths. Pricing presents product-level Free, Starter, Growth, and Pro Bundle plans. Public integrations distinguishes native integrations from webhook/API-compatible workflows. Knowledge Base exposes product guides, setup, automation, customer data, API reference, and AI-readable docs. No horizontal overflow was measured at four viewports with desktop UA. At 1024px, the hero conversation card overlaps supporting copy and part of the CTA row. At 768px and 390px, public navigation collapses and hero buttons remain reachable.
- Side-effect classification: Read-only.
- Automated evidence: `PUB-01-S01`–`PUB-01-S11`.

### Authenticated scenario notes

- `AUTH-01`: Existing account login succeeded once. Credentials were read from `creds.txt` in memory only and never copied to reports or evidence.
- `ONB-01`: The existing account was inspected without creating a workspace. Onboarding surfaced clear checklist labels, but integration prerequisites and progress behavior need sharper explanation.
- `NAV-01`: All 14 global destinations loaded. One wait strategy was too strict; bounded recovery succeeded without changing the test boundary.
- `AI-01`, `CHAT-01`, `CRM-01`, `LINK-01`, and `COM-01`: Capability surfaces were inspected with empty-state or gated-state limitations recorded above. No message, contact, upload, order, payment, publish, or OAuth operation was performed.
- `INT-01`, `PLAN-01`, and `DOC-01`: Integration coverage, plan gates, packaging, and setup documentation were captured from authenticated/public surfaces.
- `X-01`: Responsive checks confirm no horizontal overflow but expose a repeated mobile header collision.
