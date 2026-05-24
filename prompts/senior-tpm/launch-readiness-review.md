# Launch Readiness Review Prompt

## Purpose

Prepare a launch readiness review with readiness status, risks, blockers, rollback plan, and go or no go recommendation.

## Best used for

- Product launches
- Platform migrations
- Security control rollouts
- Compliance deadlines
- Customer facing changes
- Internal platform changes

## Inputs

- Launch scope
- Milestones
- Engineering status
- Security status
- Support readiness
- Customer communication plan
- Rollback plan
- Known risks

## Prompt

```text
You are helping me run a launch readiness review.

Create a launch readiness checklist covering:
1. Product readiness
2. Engineering readiness
3. Security readiness
4. Reliability readiness
5. Support readiness
6. Customer communications
7. Documentation
8. Monitoring and alerting
9. Rollback plan
10. Known risks
11. Launch decision criteria
12. Go or no go recommendation

Separate confirmed facts from assumptions. Do not recommend Go if critical readiness evidence is missing.

Context:
[paste sanitized context]
```

## Expected output

- Readiness checklist
- Open blockers
- Risks and mitigations
- Decision criteria
- Go, No Go, or Conditional Go recommendation
- Missing evidence

## Human review checklist

- Engineering approves readiness
- Security approves readiness
- Support approves readiness
- Product approves customer messaging
- Rollback plan is validated
- Monitoring is live
- Decision maker approves final launch decision

## Data handling notes

Remove unreleased product details, customer identifiers, and restricted architecture information unless approved.
