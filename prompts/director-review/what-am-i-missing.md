# What Am I Missing Prompt

## Use this when

A plan looks reasonable, but the TPM wants a second pass for hidden risks, missing owners, weak assumptions, and gaps in the operating model.

## Why it matters

This is the prompt for the moment when something feels fine, which is exactly when it is worth checking. A fresh review can find the loose end before it becomes the escalation.

## Inputs to gather

- Program plan
- Current risks
- Dependencies
- Stakeholders
- Timeline
- Metrics
- Known open questions

## Prompt

```text
Review the sanitized program context below and tell me what I may be missing.

Look for:
1. Missing stakeholders
2. Hidden dependencies
3. Unclear ownership
4. Weak success metrics
5. Timeline risk
6. Compliance or security gaps
7. Customer impact gaps
8. Operational readiness gaps
9. Decisions that are implied but not named
10. Questions I should answer before the next review

Be direct. I would rather find the gap now than in the executive review.

Context:
[paste sanitized context]
```

## Expected output

- Potential gaps
- Questions to answer
- Hidden dependencies
- Ownership issues
- Risks to add to RAID
- Recommended next action

## Human review checklist

- The output separates real gaps from guesses
- Questions are specific
- Risks are not exaggerated
- Next action is clear
- Sensitive details are removed


## Data handling notes

Sanitize internal, customer, security, legal, and commercial details before prompting.


## Done when

The review is ready when it gives the TPM at least one concrete thing to confirm, close, or escalate.
