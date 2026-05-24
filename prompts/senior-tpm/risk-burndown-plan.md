# Risk Burndown Plan Prompt

## Purpose

Create a structured plan to reduce top program risks before a key milestone.

## Best used for

- Executive reviews
- Pre launch reviews
- Security programs
- Compliance deadlines
- Platform migrations
- Customer commitments

## Inputs

- Program objective
- Target milestone
- Known risks
- Owners
- Current mitigations
- Escalation thresholds

## Prompt

```text
You are helping me create a risk burndown plan for a complex program.

Identify the top risks and create a mitigation plan for each.

For each risk, include:
1. Risk statement
2. Probability
3. Impact
4. Detection signal
5. Mitigation
6. Contingency
7. Owner
8. Deadline
9. Escalation threshold
10. Current status

Separate risks from active issues. Do not invent owners or deadlines. Mark unclear items as "Needs confirmation."

Context:
[paste sanitized context]
```

## Expected output

- Risk burndown table
- Top risk narrative
- Immediate actions
- Escalation thresholds

## Human review checklist

- Validate probability and impact
- Confirm owners
- Confirm mitigation feasibility
- Add accepted risks to the proper approval process
- Update the official RAID log

## Data handling notes

Be careful with customer impact, security severity, legal obligations, and compliance dates.
