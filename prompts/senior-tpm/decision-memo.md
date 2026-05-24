# Decision Memo Prompt

## Use this when

A program is stuck between options and needs a clear recommendation, not another open-ended discussion.

## Why it matters

Decision memos are where a TPM earns trust. The memo should make the options, tradeoffs, risks, and recommendation clear enough that the decision owner can act.

## Inputs to gather

- Decision needed
- Background
- Options considered
- Customer or business impact
- Engineering impact
- Cost or capacity impact
- Risks
- Deadline

## Prompt

```text
Help me write a decision memo using the sanitized context below.

Create a memo with:
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
12. Decision owner and needed-by date

Do not pretend the options are equal if the evidence supports a recommendation. Also do not hide the tradeoffs just because the recommendation is clear.

Context:
[paste sanitized context]
```

## Expected output

- Decision summary
- Background
- Options table
- Recommendation
- Tradeoffs
- Risks
- Impact summary
- Decision owner and date

## Human review checklist

- Recommendation is supported by evidence
- Tradeoffs are honest
- No option is oversold
- Decision owner is named
- Consequences of waiting are clear
- Sensitive data is removed


## Data handling notes

Remove customer, financial, legal, and security details unless approved for use.


## Done when

The memo is ready when the decision owner can say yes, no, or needs more data without first asking what the decision is.
