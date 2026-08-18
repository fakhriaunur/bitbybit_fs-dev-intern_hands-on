# Evaluation Matrix

## Report status

- Status: `PASS`
- Evidence completeness: `PARTIAL` — strong surface coverage, but outbound/integration/publish flows were intentionally not exercised

## Scoring method

```text
combined score = (0.60 × automated score) + (0.40 × discretionary score)
weighted points = (combined score ÷ 5) × weight
overall score = sum(weighted points)
```

Scores reflect observed product behavior, not marketing claims. Automated scores include route/scenario evidence and exploratory performance checks. Discretionary scores include usability, clarity, workaround cost, and product-fit judgment.

## Weighted score

| Criterion | Weight | Automated score | Discretionary score | Combined score | Weighted points | Evidence IDs | Confidence | Notes |
|---|---:|---:|---:|---:|---:|---|---|---|
| Workflow functionality and completion | 25 | `3.7` | `3.6` | `3.7` | `18.3` | `AUTH-01-S01`–`COM-01-S03` | Medium | Broad route coverage and clear controls; many completion paths lacked seeded data or were stopped at side-effect boundaries. |
| Feature depth and usefulness | 20 | `4.2` | `4.0` | `4.1` | `16.5` | `AI-01-S01`–`AI-01-S03`, `CHAT-01-S01`–`CHAT-01-S06`, `CRM-01-S01`–`CRM-01-S05`, `LINK-01-S01`–`LINK-01-S03`, `COM-01-S01`–`COM-01-S03` | Medium | AI, support, CRM, commerce, link, tagging, and template surfaces form a coherent breadth story. |
| Integrations and interoperability | 20 | `4.1` | `3.7` | `3.9` | `15.8` | `INT-01-S01`–`INT-01-S02`, `COM-01-S02`, `DOC-01-S01`–`DOC-01-S02` | High | Strong channel/Shopify/Indonesia coverage and Shopee import workaround; developer/API capability is plan-gated. |
| Performance and reliability | 15 | `4.1` | `3.8` | `4.0` | `11.9` | `PUB-01-S07`–`PUB-01-S08`, `X-01-S02`–`X-01-S03` | Medium | No captured page errors and acceptable single-run timings; one wait strategy timed out and samples are not repeatable SLA data. |
| Onboarding, UX, accessibility, responsiveness | 10 | `3.7` | `3.2` | `3.5` | `7.0` | `PUB-01-S01`–`PUB-01-S04`, `ONB-01-S01`–`ONB-01-S03`, `X-01-S01` | High | No overflow, but 390px header collision repeats across critical authenticated routes; 1024px public hero overlap remains. |
| Pricing, limits, and product fit | 10 | `3.6` | `3.5` | `3.6` | `7.1` | `PUB-01-S09`, `PLAN-01-S01`, `INT-01-S02`, `LINK-01-S03` | High | Free/product-level packaging is visible; cross-product plan state, referral/access paths, and gate rationale need clarity. |
| **Total** | **100** | | | | **`76.6 / 100`** | | **Medium** | Strong breadth and integration story, with onboarding clarity and compact-header polish as primary friction. |

## Functional and feature evidence

| Finding | Automated evidence | Discretionary evidence | Combined assessment | Confidence |
|---|---|---|---|---|
| 14 authenticated global routes load | `NAV-01-S01` | Route taxonomy is broad and consistent | Strong discoverability; route-level breadth is proven, task completion is not | High |
| AI agent/knowledge/tagging surfaces | `AI-01-S01`–`AI-01-S03` | Agent concepts are coherent; publish guardrail still untested | High feature breadth with incomplete lifecycle validation | Medium |
| Support workspace | `CHAT-01-S01`–`CHAT-01-S06` | Search/filter/assignment controls are discoverable; empty inbox limits confidence | Useful support shell, partial workflow proof | Medium |
| CRM and customer data | `CRM-01-S01`–`CRM-01-S05` | Import history and filters help explain record model; Customer Sync is unclear | Partial CRM activation path | Medium |
| Commerce catalog | `COM-01-S01`–`COM-01-S03` | Shopee Beta mapping is differentiated; no import/order proof by design | Strong read-only catalog evidence, incomplete transaction proof | High |
| bitLink builder | `LINK-01-S01`–`LINK-01-S03` | Preview and controls are rich; publish boundary preserved | Good draft surface, preview update unverified | Medium |

## Performance evidence

| Metric/finding | Automated evidence | Discretionary interpretation | Assessment | Confidence |
|---|---|---|---|---|
| Public landing vitals | `PUB-01-S08` | TTFB 84.3ms, FCP 384ms, LCP 444ms, CLS 0.04 in one run | Fast exploratory public sample | Medium |
| Authenticated route vitals | `X-01-S02` | Home LCP 2756ms; AI Studio 1664ms; Integrations 1800ms; CLS 0–0.04 | Normal app rendering, Home merits optimization/repeat measurement | Medium |
| Error/recovery behavior | `AUTH-01-S01`, `NAV-01-S01`, `X-01-S03` | No captured page errors; one network-idle timeout recovered with bounded wait | Reliable enough for exploratory run; strengthen wait strategy | Medium |
| Responsive overflow | `PUB-01-S01`–`PUB-01-S04`, `X-01-S01` | No horizontal overflow, but compact header collision at 390px | Functional layout mostly holds; visual/accessibility defect remains | High |

## Benchmark evidence

| Capability | bitbybit | Competitor reference | Comparable? | Source/evidence IDs | Notes |
|---|---|---|---|---|---|
| WhatsApp support/inbox | Livechat, tickets, chatbot, forms, widget | WATI team inbox; respond.io unified inbox; SleekFlow omnichannel AI | Partial | `CHAT-01-S01`–`CHAT-01-S06`, `SRC-04`, `SRC-06`, `SRC-09` | Competitor values are public-source estimates. |
| AI commerce | AI Studio, Commerce, Shopee import, Shopify surfaces | WATI, respond.io, and SleekFlow publicly position AI/commerce workflows | Partial | `AI-01-S01`–`AI-01-S03`, `COM-01-S02`, `SRC-04`, `SRC-06`, `SRC-09` | Runtime conversion/order parity not tested. |
| Integration model | Native connectors plus gated Developer/API capability and docs | Make/n8n/API2Cart optimize broader workflow/connectivity | No | `INT-01-S01`–`INT-01-S02`, `SRC-13`–`SRC-15` | Appendix comparison only; different products. |
