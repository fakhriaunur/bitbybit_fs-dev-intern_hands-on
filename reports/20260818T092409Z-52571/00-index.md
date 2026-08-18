# Run Index

## Run metadata

| Field | Value |
|---|---|
| Run ID | `20260818T092409Z-52571` |
| Date/time UTC | `2026-08-18 09:24–11:09 UTC` |
| Driver | `droid-control / agent-browser` |
| Browser | `agent-browser 0.27.0 / HeadlessChrome 152.0.0.0` |
| User agent | Desktop Chrome UA retained while viewport changed |
| Account mode | Existing candidacy account |
| Viewports | `1440x900`, `1024x768`, `768x1024`, `390x844` |
| Safety boundary | Product-only; no external integrations or real-world side effects |

## Status summary

| Status | Count |
|---|---:|
| PASS | `6` |
| PARTIAL | `7` |
| FAIL | `0` |
| BLOCKED | `0` |
| NOT TESTED | `0` |

## Evidence index

Raw evidence stayed outside repository. Authenticated snapshots and screenshots contained account UI and were marked temporary-only; they are deleted during final cleanup. Findings copied into reports contain no credentials, cookies, tokens, customer records, or private account values.

| Evidence ID | Type | Scenario | Viewport/scope | Artifact | Redaction check |
|---|---|---|---|---|---|
| `PUB-01-S01`–`PUB-01-S05` | Screenshots | `PUB-01` | Four viewports plus scroll | `/tmp/bitbybit-explore-20260818T092409Z-52571/evidence/PUB-01-*.png` | `PASS` |
| `PUB-01-S06`, `PUB-01-S09`–`PUB-01-S11` | Accessibility snapshots | `PUB-01` | Landing, pricing, integrations, docs | `/tmp/bitbybit-explore-20260818T092409Z-52571/evidence/PUB-01-*.snapshot.txt` | `PASS` |
| `PUB-01-S07`–`PUB-01-S08` | Diagnostics/vitals | `PUB-01` | Public landing | `/tmp/bitbybit-explore-20260818T092409Z-52571/evidence/PUB-01-page-errors.txt`, `PUB-01-vitals.json` | `PASS` |
| `AUTH-01-S01`–`AUTH-01-S02` | Login/baseline snapshots | `AUTH-01` | Existing account | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `NAV-01-S01` | Route result manifest | `NAV-01` | 14 authenticated routes | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `ONB-01-S01`–`ONB-01-S03` | Onboarding snapshots/body | `ONB-01` | Existing bitChat onboarding | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `AI-01-S01`–`AI-01-S03` | AI Studio snapshots | `AI-01` | Agent, knowledge, tagging | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `CHAT-01-S01`–`CHAT-01-S06` | Inbox/support snapshots | `CHAT-01` | Livechat, ticket, chatbot, form, widget | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `CRM-01-S01`–`CRM-01-S05` | CRM snapshots | `CRM-01` | Customers, segments, import, sync | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `LINK-01-S01`–`LINK-01-S03` | bitLink snapshots | `LINK-01` | Appearance, social, subscription | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `COM-01-S01`–`COM-01-S03` | Commerce snapshots | `COM-01` | Orders, products, vouchers | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `INT-01-S01`–`INT-01-S02` | Integration/developer snapshots | `INT-01` | Catalog and plan gate | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `PLAN-01-S01` | Plan-management snapshot/body | `PLAN-01` | Free plan and balances | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |
| `DOC-01-S01`–`DOC-01-S02` | Public docs snapshots/body | `DOC-01` | Docs index and WhatsApp setup | `/tmp/bitbybit-explore-20260818T092409Z-52571/evidence/DOC-01-*.snapshot.txt` | `PASS` |
| `X-01-S01`–`X-01-S03` | Responsive manifest/timings/vitals | `X-01` | Four routes, four viewports | Temporary authenticated evidence; deleted before commit | `PASS — findings sanitized` |

## Run notes

- Login result: `PASS`; existing account reached authenticated home.
- Manual intervention: none; headless browser remained sufficient.
- External actions avoided: yes; no OAuth, messaging, imports, payments, orders, publishing, upgrades, or API-key creation.
- Recovery: one network-idle navigation wait timed out on Misc; bounded wait and route inspection recovered the run.
- Temporary fixture cleanup: no fixture or uploaded file created.
- Browser/session cleanup: browser closed; authenticated evidence removed.
