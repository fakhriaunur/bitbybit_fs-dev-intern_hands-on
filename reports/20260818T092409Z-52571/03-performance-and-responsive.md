# Performance and Responsive Findings

## Report status

- Status: `PARTIAL`
- Evidence completeness: `PASS` for captured routes; timing samples are exploratory, not SLA evidence

## Run conditions

| Field | Value |
|---|---|
| Browser/OS | `agent-browser 0.27.0 / HeadlessChrome 152.0.0.0 / Linux` |
| Network condition | Default workspace network; not throttled |
| Cache state | Isolated browser session; route samples include normal app cache/runtime |
| Desktop user agent retained | `Yes` |
| Viewports | `1440x900`, `1024x768`, `768x1024`, `390x844` |

## Timing summary

All values are one-run exploratory measurements. `p50`/`p95` are not reported because sample count is one per route.

| Route/action | Viewport | Samples | DCL (ms) | Load (ms) | TTFB (ms) | FCP (ms) | LCP (ms) | CLS | Errors/timeouts | Evidence IDs | Notes |
|---|---|---:|---:|---:|---:|---:|---:|---:|---|---|---|
| Public landing Core Web Vitals | `1440x900` | `1` | — | — | `84.3` | `384` | `444` | `0.04` | `0 page errors` | `PUB-01-S07`–`PUB-01-S08` | Fresh public sample; not SLA evidence. |
| Authenticated Home | `1440x900` | `1` | `1609` | `1615` | `3.5` | `2260` | `2756` | `0` | `0 page errors` | `X-01-S02` | LCP dominated by app content; one route sample. |
| Authenticated AI Studio | `1440x900` | `1` | `541` | `543` | `3.5` | `1540` | `1664` | `0` | `0 page errors` | `X-01-S02` | Stable route after fixed wait. |
| Authenticated Integrations | `1440x900` | `1` | `485` | `487` | `5.0` | `1664` | `1800` | `0.04` | `0 page errors` | `X-01-S02` | Stable catalog after fixed wait. |

## Responsive matrix

| Surface | 1440x900 | 1024x768 | 768x1024 | 390x844 | Defect/evidence IDs |
|---|---|---|---|---|---|
| Public landing | `PASS` | `PARTIAL` | `PASS` | `PASS` | `PUB-01-S01`–`PUB-01-S04`; 1024px hero overlap |
| Home | `PASS` | `PASS` | `PASS` | `PARTIAL` | `X-01-S01`; compact-header collision |
| Onboarding/inbox entry | `PASS` | `PASS` | `PASS` | `PARTIAL` | `X-01-S01`; compact-header collision |
| AI Studio | `PASS` | `PASS` | `PASS` | `PARTIAL` | `X-01-S01`; compact-header collision |
| Integrations | `PASS` | `PASS` | `PASS` | `PARTIAL` | `X-01-S01`; compact-header collision |

## Quality checks

- Horizontal overflow: No overflow measured on four public viewports or 16 authenticated route/viewport checks.
- Header collision: At 390px, hamburger, product mark, and long account label overlap on all four authenticated routes checked. Body controls remain reachable; classify as major visual/accessibility polish issue, not navigation blocker.
- Public hero: At 1024x768, left conversation card overlaps supporting copy and part of CTA row.
- Clipped controls: No other clipped controls observed in sampled screenshots.
- Dialog/modal accessibility: Promotional modal was dismissed; systematic focus traversal was not run.
- Focus order: Not measured; follow-up required after header fix.
- Console/page errors: Captured error files were empty for inspected routes. One network-idle wait timed out on Misc, but bounded recovery succeeded.
- Recovery behavior: Partial pass; explicit recovery was demonstrated for navigation wait timeout.
