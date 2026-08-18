# Evaluation Matrix and Scoring Rubric

## Score anchors

Use integer or one-decimal scores from 0 to 5:

| Score | Meaning |
|---:|---|
| 5 | Complete, clear, reliable, and evidence-backed |
| 4 | Works with minor friction |
| 3 | Usable but partial, limited, or workaround-dependent |
| 2 | Major friction or unreliable path |
| 1 | Barely usable, mostly blocked, or unclear |
| 0 | Unavailable, broken, or contradicted by evidence |

Do not award a score from marketing claims alone. A public claim can be a benchmark data point, not proof of in-product behavior.

## Weighted criteria

| Criterion | Weight | Automated evidence | Discretionary evidence |
|---|---:|---|---|
| Workflow functionality and completion | 25 | Scenario completion, pass rate, recoverability, visible confirmations | Task usefulness, ambiguity, workaround cost |
| Feature depth and usefulness | 20 | Surface/capability coverage and control behavior | Product coherence, quality, missing capabilities |
| Integrations and interoperability | 20 | Native integrations, webhook/API paths, setup docs, errors | Stack fit, missing marketplaces, integration effort |
| Performance and reliability | 15 | p50/p95 timings, errors, timeout rate, repeatability | Perceived speed, stability, confidence under normal use |
| Onboarding, UX, accessibility, responsiveness | 10 | Viewport evidence, focus/accessibility checks, route success | Learnability, clarity, friction, visual hierarchy |
| Pricing, limits, and product fit | 10 | Plan/gate evidence, limits, feature visibility | Value, packaging, fit for operator/developer/student |
| **Total** | **100** |  |  |

## Formula

For each criterion:

```text
combined score = (0.60 × automated score) + (0.40 × discretionary score)
weighted points = (combined score ÷ 5) × criterion weight
overall score = sum(weighted points)
```

Example:

```text
automated = 4.0
discretionary = 3.5
combined = (0.60 × 4.0) + (0.40 × 3.5) = 3.8
criterion weight = 25
weighted points = (3.8 ÷ 5) × 25 = 19.0
```

Round displayed scores to one decimal. Keep enough precision internally to avoid rounding drift.

## Confidence

Confidence is separate from score:

- `High`: direct evidence from repeated scenarios and at least two evidence types.
- `Medium`: direct evidence from one route or one run, or a partly comparable public source.
- `Low`: inferred, blocked, single observation, or public claim without product confirmation.

Missing evidence lowers confidence. It does not become a zero unless the product was actually tested and failed or the capability was confirmed unavailable.

## Automated quality metrics

Record where measurable:

| Metric | Definition |
|---|---|
| Scenario pass rate | `PASS / (PASS + PARTIAL + FAIL + BLOCKED)` with `NOT TESTED` excluded |
| Route success rate | Stable loaded routes / attempted routes |
| Action latency | Time from action to visible stable result |
| Navigation timing | `domContentLoaded`, `load`, and `PerformanceNavigationTiming` values |
| Paint timing | FCP/LCP when exposed by browser |
| Error rate | Failed requests, page errors, and console errors per scenario |
| Recovery rate | Recoverable interruptions / interruptions |
| Responsive defects | Count by severity: blocker, major, minor |

Do not present these as production SLAs. Label them as exploratory observations with run conditions.

## Target-product matrix

Copy this table into `05-evaluation-matrix.md`:

| Criterion | Weight | Automated score (0-5) | Discretionary score (0-5) | Combined score | Weighted points | Evidence IDs | Confidence | Notes |
|---|---:|---:|---:|---:|---:|---|---|---|
| Workflow functionality and completion | 25 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| Feature depth and usefulness | 20 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| Integrations and interoperability | 20 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| Performance and reliability | 15 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| Onboarding, UX, accessibility, responsiveness | 10 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| Pricing, limits, and product fit | 10 | `TBD` | `TBD` | `TBD` | `TBD` |  |  |  |
| **Total** | **100** |  |  |  | **TBD / 100** |  |  |  |

## Competitor benchmark matrix

Use two layers, without false equivalence:

### Layer 1: WhatsApp-first AI commerce

Primary cohort: bitbybit, WATI, respond.io, SleekFlow, Gorgias.

### Layer 2: Integration operating model

Secondary cohort: bitbybit, SAAS Integrator, API2Cart, Make, n8n.

| Capability | Product | Evidence class | Finding/value | Source URL | Retrieved UTC | Confidence | Comparable? |
|---|---|---|---|---|---|---|---|
| Commerce/catalog | `<product>` | `Observed/Public-source estimate/Not comparable` | `<finding>` | `<url>` | `<date>` | `High/Medium/Low` | `Yes/Partial/No` |

If Layer 2 cannot be compared fairly, retain it as an integration-operating-model appendix and use WATI, respond.io, and SleekFlow as the WhatsApp-first fallback cohort. Record why in the report.
