# Bitbybit Exploration Reports

Reports are generated per isolated run. Do not put credentials, cookies, tokens, raw private customer data, or persistent browser state in this directory.

## Create a run

1. Generate a unique run ID.
2. Copy `reports/_template/` to `reports/<run-id>/`.
3. Keep raw screenshots, snapshots, and timing artifacts in an isolated temporary evidence directory.
4. Update Markdown modules as each scenario or benchmark batch completes.
5. Finalize `99-final-report.md` last.

## Modules

| File | Purpose |
|---|---|
| `00-index.md` | Run metadata and evidence index |
| `01-automated-exploration.md` | Scenario execution results |
| `02-discretionary-observations.md` | Manual observations and hypotheses from `takehome.md` |
| `03-performance-and-responsive.md` | Browser timings, errors, viewport checks |
| `04-competitor-benchmark.md` | Dated public-source competitor evidence |
| `05-evaluation-matrix.md` | Automated/discretionary scores and weighted total |
| `06-questions-and-recommendations.md` | Interview questions and prioritized recommendations |
| `99-final-report.md` | Short consolidated summary |

## Status vocabulary

Use only:

`PASS` · `PARTIAL` · `FAIL` · `BLOCKED` · `NOT TESTED`

## Evidence policy

Evidence paths should be relative to the run's external evidence directory. Redaction status is required for every evidence item. Never copy auth state into this repository.
