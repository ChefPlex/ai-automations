# Technical Tradeoff Analysis Prompt

## Use this when

A program needs to compare technical options and the TPM needs to frame the tradeoffs clearly for engineering and leadership.

## Why it matters

Tradeoff analysis is not about making the TPM the architect. It is about making the decision visible: customer impact, complexity, risk, reversibility, timing, and long-term cost.

## Inputs to gather

- Options under consideration
- Customer impact
- Engineering constraints
- Security considerations
- Reliability considerations
- Compliance needs
- Timeline
- Operational impact

## Prompt

```text
Use the sanitized context below to compare the technical options.

Compare each option across:
1. Customer impact
2. Engineering complexity
3. Security risk
4. Reliability risk
5. Operational burden
6. Compliance impact
7. Time to deliver
8. Long-term maintainability
9. Reversibility
10. Recommendation

Make assumptions explicit and identify where engineering input is required.

Context:
[paste sanitized context]
```

## Expected output

- Comparison table
- Assumptions
- Recommendation
- Tradeoffs
- Engineering questions
- Decision needed

## Human review checklist

- Technical claims are validated or marked for engineering review
- Security and reliability risks are not softened
- Recommendation is tied to evidence
- Reversibility is addressed
- Missing data is visible


## Data handling notes

Remove proprietary architecture details, vulnerability details, source code, and internal links unless approved.


## Done when

The analysis is ready when engineering can correct the technical details and leadership can understand the tradeoff.
