# Questions and Recommendations

## Report status

- Status: `PASS`
- Evidence completeness: `PARTIAL` — recommendations are evidence-backed; destructive or externally connected flows were not exercised by design

## Prioritized recommendations

| Priority | Recommendation | User/problem | Evidence IDs | Expected impact | Effort estimate | Confidence |
|---|---|---|---|---|---|---|
| P0 | Fix compact authenticated header layout at 390px. Collapse or truncate account identity, reserve hamburger/logo slots, and verify focus order. | Mobile users see hamburger, bitbybit mark, and account label overlap on every critical route tested. | `X-01-S01`, temporary `X-01-*-390x844.png` | Removes repeated visual ambiguity and improves mobile navigation/accessibility confidence. | Medium | High |
| P1 | Make onboarding prerequisites and progress state explicit. Show why Continue cannot advance, distinguish connected versus locked skills, and link setup docs at each gate. | Existing onboarding showed 20% progress, WhatsApp-not-connected, locked commerce skills, and no visible Continue transition. | `ONB-01-S01`–`ONB-01-S03`, `DOC-01-S01`–`DOC-01-S02`, `INT-01-S02` | Shortens time-to-first-value and reduces support dependence. | Medium | High |
| P1 | Provide a safe demo/seed state for inbox, CRM, and Commerce QA. | Empty inbox/orders/customers prevent validation of search, handoff, customer context, catalog, and order workflows without side effects. | `CHAT-01-S01`–`CHAT-01-S06`, `CRM-01-S01`–`CRM-01-S05`, `COM-01-S01`–`COM-01-S03` | Enables reliable product tours, QA, and interviews without real customer/order data. | High | High |
| P1 | Repair or remove Customer Sync destination and explain sync permissions. | Settings menu exposes Customer Sync, but captured query loads only the settings shell with no substantive controls. | `CRM-01-S04`–`CRM-01-S05` | Prevents dead-end navigation and clarifies privacy/data movement. | Medium | Medium |
| P2 | Surface marketplace coverage and workaround policy. Keep Shopee Beta mapping visible in docs; state whether Tokopedia, Lazada, and Blibli require CSV, API, or roadmap support. | Public connector catalog does not show those marketplaces, while Commerce does show a Shopee import path. | `INT-01-S01`, `COM-01-S02`, `PUB-01-S10` | Improves regional merchant fit and avoids false integration expectations. | Low | High |
| P2 | Improve plan/gate transparency. Show which product plan unlocks Developer/API tools, what “No plan yet” means, and whether referrals/student/experimental access exist. | Developer tools are Standard+ gated; several product plans are empty; public pricing does not answer access-program questions. | `INT-01-S02`, `PLAN-01-S01`, `LINK-01-S03` | Makes packaging legible and reduces unsafe upgrade exploration. | Medium | High |
| P2 | Fix public 1024px hero composition. | Supporting copy and CTA row are partially overlapped by conversation artwork at a common laptop viewport. | `PUB-01-S02` | Improves first-impression polish without changing narrative. | Low | High |

## Interview questions

| Question | Trigger/evidence | Why it matters | Open/answered |
|---|---|---|---|
| Is onboarding goal selection intentionally single-select, or should operators choose multiple goals? | `H-02`, `ONB-01-S01`–`ONB-01-S03` | Determines whether onboarding captures useful intent. | `OPEN` |
| Is the text-box scroll/autoclose behavior known or expected? | `H-01`, `ONB-01-S01`–`ONB-01-S03` | Separates a take-home hypothesis from a reproducible defect. | `OPEN` |
| Why did the captured onboarding Continue state not visibly advance, and how is progress persisted? | `ONB-01-S01`–`ONB-01-S03` | Clarifies whether this is a prerequisite gate, state bug, or expected empty state. | `OPEN` |
| Are referral codes, a-la-carte pricing, usage-based options, or student access planned? | `H-03`, `H-08`, `PLAN-01-S01`, `INT-01-S02` | Tests product fit for narrow-entry and early-adopter segments. | `OPEN` |
| What is the intended balance between Knowledge Base documentation and chat support? | `H-04`, `DOC-01-S01`–`DOC-01-S02` | Guides investment in self-service and setup completion. | `OPEN` |
| Is bitLink literal text part of brand language or a rendering limitation? | `H-05`, `LINK-01-S01`–`LINK-01-S03` | Avoids treating intentional editable branding as a defect. | `OPEN` |
| What is the strategy for Shopee, Tokopedia, Lazada, Blibli, and other non-native marketplaces? | `H-06`, `INT-01-S01`, `COM-01-S02` | Distinguishes native connector roadmap from import workaround. | `OPEN` |
| Are Google Contacts or WhatsApp contact-sync workflows in scope, and what should Customer Sync expose? | `H-07`, `CRM-01-S04`–`CRM-01-S05` | Clarifies CRM activation and data-permission model. | `OPEN` |
| How are experimental features and developer/student access gated safely? | `H-08`, `INT-01-S02` | Explains Standard+ API gating and possible adoption programs. | `OPEN` |
| Which primary operator segment should score highest: Shopify merchant, WhatsApp support team, agency, developer, or student? | `PUB-01-S01`, `PLAN-01-S01`, `05-evaluation-matrix.md` | Sets product-fit weighting for roadmap and packaging decisions. | `OPEN` |

## Limitations

- No OAuth or external channel connection was authorized; integration setup friction beyond catalog/gate surfaces remains unmeasured.
- No messages, imports, payments, orders, publishes, API keys, upgrades, trials, or real customer data were used.
- Empty-state data limited support, CRM, Commerce, and analytics workflow completion.
- Focus traversal, keyboard-only navigation, screen-reader output, and systematic modal semantics were not fully measured.
- Competitor benchmark uses official public pages and cannot establish runtime parity, reliability, or exact plan limits.
