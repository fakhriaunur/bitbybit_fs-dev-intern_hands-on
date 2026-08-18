# Exploration Scenario Catalog

## Execution rules

- Run only against the existing candidacy account.
- Use read-only inspection or reversible synthetic fixtures labeled `QA exploratory`.
- Do not cross product-only boundaries listed in `qa/agentic-exploration-spec.md`.
- Re-snapshot after navigation or state change.
- Every scenario must end with one status: `PASS`, `PARTIAL`, `FAIL`, `BLOCKED`, or `NOT TESTED`.
- Record evidence IDs as actions complete.

## Scenario matrix

| ID | Area | Preconditions | Steps | Expected result | Side-effect class | Status | Automated evidence | Discretionary note | Follow-up |
|---|---|---|---|---|---|---|---|---|---|
| `PUB-01` | Public landing page | No login | Open landing page; inspect value proposition, product links, pricing, integrations, and knowledge base; check all four viewports | Claims are understandable; key routes resolve; no responsive clipping or broken navigation | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `AUTH-01` | Existing-account login | `creds.txt` has two records | Open login; fill existing credentials in memory; submit once; wait for stable authenticated route; capture baseline | Existing account logs in or clear redacted failure is shown | Account access | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `ONB-01` | Onboarding/workspace | Authenticated account; no new workspace | Inspect onboarding state; test goal selection; inspect scroll/autoclose behavior; do not submit new workspace creation | Existing workspace state is understandable; goal behavior is consistent and accurately labeled | Reversible internal state only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `NAV-01` | Product discovery | Authenticated account | Traverse global navigation to bitChat, bitCRM, AI Studio, Commerce, bitLink, bitLoyalty, bitApp, settings, and help; return after each route | Routes load; current location is clear; access gates explain themselves | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `AI-01` | AI Studio | Authenticated account; synthetic fixture only if required | Inspect knowledge, skills, guardrails, playground, and test/publish distinction; use `QA exploratory` fixture only if safe | Agent configuration concepts and unsafe-action controls are clear; no publish required | Reversible internal draft | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `CHAT-01` | Inbox/support | Seeded conversations or read-only view | Inspect inbox, search, filters, tags, assignment, handoff, context, and summaries; do not send or trigger messages | Conversation operations are discoverable; context survives handoff; safe boundary is visible | Read-only; no outbound communication | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `CRM-01` | Customers/CRM | Authenticated account | Inspect customer search, profile, segments, automations, and import options; do not import contacts or sync data | Customer record model and import risks are clear | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `LINK-01` | bitLink | Authenticated account; draft-only | Inspect setup, logo/text rendering, preview, mobile layout, style controls, and analytics; create no public/published link | Preview reflects settings; literal bitbybit text/logo behavior is understood; mobile layout is usable | Reversible internal draft | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `COM-01` | Commerce/catalog/orders | Authenticated account; preview/simulated data only | Inspect catalog, product details, cart, order visibility, checkout/payment boundaries, and status states; stop before real order/payment | Commerce model and guardrails are understandable; unsafe actions are gated | Read-only; no order/payment | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `INT-01` | Integrations | Authenticated account or public integration catalog | Inspect categories, filters, native versus webhook/API labels, setup docs, and missing marketplace coverage; stop before connect | Integration coverage and setup effort are explicit; unsupported Shopee/Tokopedia/Lazada/Blibli paths are distinguishable | Read-only; no authorization | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `PLAN-01` | Plans and packaging | Public pricing plus authenticated gates | Inspect free/paid limits, trials, referral/promo fields, a-la-carte wording, experimental/future features, developer/student access; do not enroll or upgrade | Limits, gates, and future features are clear; pricing hypotheses have evidence or remain open | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `DOC-01` | Documentation/help | Public or in-product docs reachable | Search knowledge base; inspect task documentation, setup prerequisites, troubleshooting, and chat-support fallback | Docs support independent task completion and distinguish docs from assisted support | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |
| `X-01` | Cross-cutting quality | At least three critical routes | Repeat critical checks at all four viewports; inspect overflow, focus order, dialogs, errors, timing, and recovery | Layout remains usable; key controls remain reachable; timing/error results are recorded | Read-only | `NOT TESTED` | `<evidence>` | `<note>` | `<follow-up>` |

## Hypotheses from discretionary notes

Question-mark observations are hypotheses. Automated evidence may confirm, refine, or reject them.

| Hypothesis ID | Source note | Test scenario | Evidence needed | Current conclusion |
|---|---|---|---|---|
| `H-01` | Onboarding option text box scroll/autoclose may glitch | `ONB-01`, `X-01` | Repeated interaction plus viewport screenshots | `OPEN` |
| `H-02` | Current goal may need multi-select | `ONB-01` | Control semantics and resulting state | `OPEN` |
| `H-03` | Referral code and a-la-carte pricing may be useful | `PLAN-01` | Public/in-app packaging evidence | `OPEN` |
| `H-04` | Docs/manuals may reduce chat-only support dependence | `DOC-01` | Search task completion and setup clarity | `OPEN` |
| `H-05` | Literal bitLink text may be intended branding, not missing logo | `LINK-01` | Rendered UI and product convention comparison | `OPEN` |
| `H-06` | Non-native marketplace integrations may need scraping or alternative workflows | `INT-01` | Native/webhook/API coverage and gap evidence | `OPEN` |
| `H-07` | Google/WhatsApp contact sync may improve CRM onboarding | `CRM-01`, `INT-01` | Import/sync options and permission boundaries | `OPEN` |
| `H-08` | Experimental access or developer/student programs may improve adoption | `PLAN-01` | Pricing/access evidence and guardrails | `OPEN` |

## Scenario result record

Copy for each completed scenario:

```markdown
### <ID> — <short title>

- Status: `PASS | PARTIAL | FAIL | BLOCKED | NOT TESTED`
- Date/time (UTC):
- Route(s):
- Viewport(s):
- Precondition:
- Steps executed:
- Expected result:
- Actual result:
- Side-effect classification:
- Automated evidence IDs:
- Discretionary observation:
- Follow-up:
```
