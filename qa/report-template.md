# Modular QA Report Template

Copy `reports/_template/` to `reports/<run-id>/` before execution. Update reports incrementally after each scenario or evidence batch.

## Required scenario result fields

Every scenario result must include:

- ID and title
- Status: `PASS`, `PARTIAL`, `FAIL`, `BLOCKED`, or `NOT TESTED`
- Preconditions
- Steps
- Expected result
- Actual result
- Side-effect classification
- Automated evidence IDs and artifact paths
- Discretionary note
- Follow-up

## Required evidence fields

Every evidence item must include:

```markdown
### <evidence-id>

- Type:
- Scenario:
- Route:
- Timestamp (UTC):
- Viewport:
- Result:
- Artifact:
- Redaction check: `PASS`
```

## Required final sections

The final report must summarize:

1. Scope and safety boundary.
2. Existing-account access result.
3. Scenario coverage and status totals.
4. Automated and discretionary findings.
5. Responsive, accessibility, performance, and reliability observations.
6. Weighted score out of 100 with confidence.
7. Two-layer competitor benchmark or documented WhatsApp-first fallback.
8. Strengths, blockers, recommendations, and interview questions.
9. Limitations and blocked actions.
10. Evidence index.

## Redaction checklist

- [ ] No username/email value appears.
- [ ] No password value appears.
- [ ] No cookie, token, authorization code, or private URL appears.
- [ ] No private customer/contact/order data appears.
- [ ] Screenshots are redacted or limited to safe product state.
- [ ] Temporary auth/session files are outside tracked report directories and removed after run.
