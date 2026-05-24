# Decision Memo Prompt

## Purpose

Create a structured memo that clarifies a decision, options, tradeoffs, recommendation, and consequences of delay.

## Best used for

- Architecture tradeoffs
- Scope decisions
- Launch decisions
- Resource allocation
- Risk acceptance
- Compliance sequencing
- Platform migration choices

## Inputs

- Decision needed
- Background
- Options
- Constraints
- Risks
- Timeline
- Stakeholders
- Recommendation, if known

## Prompt

```text
You are helping me write a decision memo as a senior TPM.

Create a structured memo with:
1. Decision needed
2. Background
3. Problem statement
4. Options considered
5. Recommendation
6. Tradeoffs
7. Risks
8. Customer impact
9. Engineering impact
10. Cost or capacity impact
11. Consequences of no decision
12. Proposed decision owner and deadline

Make assumptions explicit. Do not invent facts. Identify missing information that would improve the decision.

Context:
[paste sanitized context]
```

## Expected output

- Decision memo
- Options table
- Recommendation
- Decision owner
- Deadline
- Missing information

## Human review checklist

- Does the decision owner have authority?
- Are tradeoffs balanced?
- Are risks accurate?
- Are customer and business impacts validated?
- Is legal, security, privacy, or compliance review needed?

## Data handling notes

Remove customer names, financial details, and restricted technical specifics unless approved.
