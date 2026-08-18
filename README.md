# bitbybit_fs-dev-intern_hands-on

Take-home exploration workspace for bitbybit Studio.

## Start here

- `takehome.md`: original task instructions.
- `reports/<run-id>/02-discretionary-observations.md`: extracted manual/discretionary observations and evidence-backed refinements.
- `qa/agentic-exploration-spec.md`: approved `/droid-control` exploration plan.
- `qa/scenarios.md`: bounded scenario catalog and hypothesis list.
- `qa/prompts/explorer.md`: agent-browser control prompt.
- `qa/scoring-rubric.md`: evaluation matrix, scoring formula, and competitor framework.
- `reports/_template/`: modular report templates.

## Exploration workflow

1. Review `takehome.md` and convert question-mark notes into hypotheses.
2. Use `/droid-control` with `agent-browser`, headless first, against the existing candidacy account.
3. Read local `creds.txt` line 1 as username/email and line 2 as password in memory only. Never print or commit credentials.
4. Keep exploration product-only. Do not create accounts/workspaces, authorize integrations, import contacts, send messages, create real orders, take payments, publish campaigns, or upgrade plans.
5. Capture screenshots, accessibility snapshots, timings, errors, and evidence IDs at each scenario.
6. Check desktop and responsive viewports while retaining desktop user agent: `1440x900`, `1024x768`, `768x1024`, `390x844`.
7. Write report modules incrementally after each scenario and evidence batch.
8. If CAPTCHA, OTP, SSO, browser rendering, or an external side effect blocks progress, stop and prompt for headed/manual intervention.

## Report structure

Create one isolated report directory per run:

```text
reports/<run-id>/
  00-index.md
  01-automated-exploration.md
  02-discretionary-observations.md
  03-performance-and-responsive.md
  04-competitor-benchmark.md
  05-evaluation-matrix.md
  06-questions-and-recommendations.md
  99-final-report.md
```

Copy `reports/_template/` to begin a run. Keep screenshots, snapshots, browser state, and raw timing artifacts outside tracked Markdown. Remove temporary auth/session material after each run.

## Evaluation model

The target-product score uses six weighted criteria:

| Criterion | Weight |
|---|---:|
| Workflow functionality and completion | 25% |
| Feature depth and usefulness | 20% |
| Integrations and interoperability | 20% |
| Performance and reliability | 15% |
| Onboarding, UX, accessibility, responsiveness | 10% |
| Pricing, limits, and product fit | 10% |

Each criterion combines automated and discretionary evidence:

```text
combined score = (0.60 × automated score) + (0.40 × discretionary score)
weighted points = (combined score ÷ 5) × criterion weight
overall score = sum(weighted points) out of 100
```

Competitor review uses two layers:

- AI-commerce/omnichannel: WATI, respond.io, SleekFlow, Gorgias.
- Integration operating model: SAAS Integrator, API2Cart, Make, n8n.

If the second layer creates false equivalence, report it separately and fall back to a WhatsApp-first comparison using WATI, respond.io, and SleekFlow.