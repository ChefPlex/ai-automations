# Launch Readiness Review Prompt

## Use this when

A launch is close enough that the team needs a go or no go view across engineering, security, support, communications, and operations.

## Why it matters

Launch readiness should not be a confidence exercise. It should make gaps visible early enough to fix them, accept them, or move the date.

## Inputs to gather

- Launch scope
- Launch date
- Readiness tracker
- Jira status
- Security review status
- Support plan
- Monitoring and rollback plan
- Known risks

## Prompt

```text
Help me prepare a launch readiness review using the sanitized context below.

Create a readiness checklist covering:
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
13. Missing information

Do not recommend go unless the evidence supports it. If something is unknown, call it unknown.

Context:
[paste sanitized context]
```

## Expected output

- Readiness table
- Open blockers
- Top risks
- Decision criteria
- Go or no go recommendation
- Missing information

## Human review checklist

- Readiness status is evidence-based
- Rollback is real and tested or clearly not tested
- Support readiness is confirmed
- Security risks are approved
- Decision criteria are explicit


## Data handling notes

Remove unreleased product details, customer-specific plans, security details, and internal links unless approved.


## Done when

The review is ready when the decision owner can make a go or no go call without hunting for missing context.
