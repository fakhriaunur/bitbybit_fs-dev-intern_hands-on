# Bitbybit Agentic Exploration Specification

Status: ready for execution
Driver: `/droid-control` with `agent-browser`
Account: existing candidacy account from `creds.txt`
Product boundary: product-only, no external integrations or real-world side effects

## Objective

Explore bitbybit end to end as an ecommerce operator and developer would. Combine repeatable browser checks with discretionary product judgment. Produce evidence-backed findings, a weighted evaluation score, a competitor benchmark, and interview questions.

Public context from initial review:

- AI commerce platform covering support, marketing, and commerce.
- Product surfaces include bitChat, bitCRM, AI Studio, bitbybit Commerce, bitLink, bitLoyalty, and bitApp.
- Public integration claims include Shopify, WhatsApp, Instagram, Messenger, TikTok messaging, payments, logistics, reviews, webhooks, and API access.

## Operating policy

### Account and credentials

- Use existing account only. Do not register, reset, or create another account or workspace.
- Read line 1 of `creds.txt` as username/email and line 2 as password, in memory only.
- Never print, screenshot, persist, commit, or place credentials in prompts, reports, browser state, or logs.
- If login fails, record only the redacted failure state and stop. Do not retry invalid credentials repeatedly.

### Product-only boundary

Allowed:

- Public-site and documentation review.
- Login to existing candidacy account.
- Read-only inspection of product surfaces.
- Reversible internal drafts or synthetic fixtures labeled `QA exploratory`, only when required to test a flow.
- Deleting or resetting those synthetic fixtures after capture.

Not allowed:

- New account, workspace, trial, upgrade, or payment.
- Shopify, WhatsApp, Instagram, Messenger, TikTok, Google, payment, logistics, or other OAuth authorization.
- Contact imports, real data sync, outbound messages, broadcasts, campaigns, or notifications.
- Real cart checkout, order creation, payment, shipping booking, or customer communication.
- Publishing changes or changing production-facing settings.
- Navigating to unapproved domains, except a user-approved manual handoff.

Stop before any action that crosses this boundary. Capture the preceding state and mark scenario `BLOCKED` when no safe alternative exists.

## Browser configuration

Run headless first with:

- Desktop Chromium.
- Desktop user agent, not mobile emulation.
- Viewports: `1440x900`, `1024x768`, `768x1024`, `390x844`.
- A unique browser session and isolated temporary evidence directory per run.
- Light/default color scheme unless visual comparison requires recording the actual theme.

Record at run start:

| Field | Value |
|---|---|
| Run ID | `<UTC timestamp>-<process or random suffix>` |
| Browser | `agent-browser` + Chromium version |
| User agent | `navigator.userAgent`, redacted only if it contains sensitive data |
| Viewport set | `1440x900`, `1024x768`, `768x1024`, `390x844` |
| URLs | `bitbybit.studio`, `app.bitbybit.studio`, `knowledge.bitbybit.studio` |
| Start/end time | `<timestamp>` |
| Account mode | existing candidacy account |

Confirm user agent is desktop. Keep desktop UA during responsive viewport checks so layout behavior is isolated from device identity.

## Execution phases

### Phase 0: Preflight

1. Confirm `creds.txt` exists and has at least two records without printing contents.
2. Generate `RUN_ID` and an isolated temporary evidence directory.
3. Open public landing page and knowledge base.
4. Capture baseline screenshots, accessibility snapshots, URL, title, UA, viewport, console errors, and page errors.
5. Initialize report files from `reports/_template/`.

### Phase 1: Existing-account access

1. Open the app login page.
2. Fill credentials in memory only.
3. Submit once and wait for a stable authenticated route.
4. Capture authenticated baseline without exposing account identifiers beyond the approved account label.
5. If blocked by CAPTCHA, OTP, SSO, browser rendering, or another manual step, stop and prompt for headed intervention.

### Phase 2: Guided exploration

Run scenarios in dependency order:

1. `PUB-01`, `AUTH-01`
2. `ONB-01`, `NAV-01`
3. `AI-01`, `CHAT-01`, `CRM-01`
4. `LINK-01`, `COM-01`, `INT-01`
5. `PLAN-01`, `DOC-01`
6. `X-01` across critical routes

The agent may choose the next uncovered scenario based on visible product state, but only from `qa/scenarios.md`.

### Phase 3: Incremental reporting

Write findings as each scenario finishes. Do not wait for exploration completion.

- After each scenario: update `01-automated-exploration.md`.
- After each discretionary observation: update `02-discretionary-observations.md`.
- After each viewport batch: update `03-performance-and-responsive.md`.
- After each competitor source batch: update `04-competitor-benchmark.md`.
- Recalculate `05-evaluation-matrix.md` whenever a scored criterion changes.
- Update questions and recommendations continuously.

### Phase 4: Closeout

1. Recheck no external action occurred.
2. Remove temporary synthetic fixtures.
3. Close browser session.
4. Remove temporary auth/session material.
5. Verify evidence and Markdown completeness.
6. Finalize `99-final-report.md` only after all other modules are current.

## Evidence contract

Use evidence IDs such as:

`PUB-01-S01`, `AUTH-01-S02`, `X-01-390-S03`

Each evidence item should contain:

| Field | Requirement |
|---|---|
| ID | Unique and referenced by report rows |
| Type | Screenshot, accessibility snapshot, console log, timing, observation |
| Source | Scenario ID and route |
| Timestamp | UTC |
| Viewport | Exact dimensions |
| Result | What evidence proves |
| Artifact | Relative path under run evidence directory |
| Redaction | Confirm no credential, token, private customer data, or session cookie |

Always take screenshots for visual QA. Text snapshots alone cannot establish responsive layout, clipping, z-index, or visual hierarchy.

## Recovery and stop conditions

Stop and capture state on:

- External authorization or account chooser.
- Destructive confirmation.
- Payment, order, shipment, campaign, broadcast, or outbound message action.
- Unexpected data loss or irreversible setting change.
- CAPTCHA, OTP, SSO, or manual browser requirement.
- Two consecutive recovery failures.

For a safe browser failure: record URL, visible error, console/page error, screenshot, and last successful evidence ID. Do not include raw request headers, cookies, tokens, or credentials.

## Deliverables

Reusable contracts:

- `qa/scenarios.md`
- `qa/prompts/explorer.md`
- `qa/scoring-rubric.md`
- `qa/report-template.md`

Per-run report:

- `reports/<run-id>/00-index.md`
- `reports/<run-id>/01-automated-exploration.md`
- `reports/<run-id>/02-discretionary-observations.md`
- `reports/<run-id>/03-performance-and-responsive.md`
- `reports/<run-id>/04-competitor-benchmark.md`
- `reports/<run-id>/05-evaluation-matrix.md`
- `reports/<run-id>/06-questions-and-recommendations.md`
- `reports/<run-id>/99-final-report.md`
