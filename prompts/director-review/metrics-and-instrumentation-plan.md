# Metrics and Instrumentation Plan Prompt

## Use this when

A program needs better metrics than percent complete and a few optimistic milestone dates.

## Why it matters

Metrics should tell the team whether risk is going down, quality is improving, adoption is happening, and the program is producing the outcome it promised.

## Inputs to gather

- Program objective
- Business or customer goal
- Current metrics
- Source systems
- Milestones
- Risks
- Teams involved

## Prompt

```text
Help me define a metrics and instrumentation plan using the sanitized context below.

Create a plan with:
1. Outcome metrics
2. Execution metrics
3. Quality metrics
4. Risk metrics
5. Adoption metrics
6. Customer impact metrics
7. Operational health metrics
8. Data source for each metric
9. Review cadence
10. Owner

Also identify metrics that look useful but may be misleading.

Context:
[paste sanitized context]
```

## Expected output

- Metrics plan
- Data sources
- Review cadence
- Owners
- Misleading metrics to avoid
- Open instrumentation gaps

## Human review checklist

- Metrics connect to outcomes
- Data sources are real
- Owners are clear
- Review cadence is reasonable
- Misleading metrics are flagged


## Data handling notes

Remove sensitive customer, production, commercial, and security details unless approved.


## Done when

The plan is ready when the team can tell whether the program is getting healthier or just getting busier.
