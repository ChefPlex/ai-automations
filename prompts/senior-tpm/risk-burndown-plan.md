# Risk Burndown Plan Prompt

## Use this when

A program has real risk and needs a plan to reduce it, not just a list of concerns.

## Why it matters

Risk management is only useful when it changes behavior. Each risk needs a signal, owner, mitigation, contingency, and point where it must be escalated.

## Inputs to gather

- Program context
- Known risks
- Milestones
- Owners
- Dependencies
- Current mitigations
- Escalation path

## Prompt

```text
Use the sanitized context below to create a risk burndown plan.

For each risk, include:
1. Risk statement
2. Probability
3. Impact
4. Detection signal
5. Mitigation
6. Contingency
7. Owner
8. Deadline
9. Escalation point
10. Current status

Then identify the top three risks that need attention this week.

Context:
[paste sanitized context]
```

## Expected output

- Risk table
- Top three risks this week
- Missing owners or dates
- Escalation recommendations

## Human review checklist

- Risks are specific and future-looking
- Detection signals are measurable
- Mitigations are real actions
- Contingencies are clear
- Owners and deadlines are present or marked missing


## Data handling notes

Do not include restricted security, customer, legal, or incident details unless approved for the tool.


## Done when

The plan is ready when the team knows what to do this week to reduce the largest risk.
