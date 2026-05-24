# Technical Tradeoff Analysis Prompt

## Purpose

Prepare for a technical decision by comparing options across customer impact, engineering complexity, security risk, reliability, operational burden, compliance impact, and reversibility.

## Best used for

- Architecture reviews
- Migration planning
- Platform design choices
- Security controls
- Reliability improvements
- Build versus buy decisions

## Inputs

- Options being considered
- Technical constraints
- Customer impact
- Timeline
- Risk context
- Engineering feedback

## Prompt

```text
You are helping a senior TPM prepare for a technical tradeoff discussion.

Analyze the options below and compare them across:
1. Customer impact
2. Engineering complexity
3. Security risk
4. Reliability risk
5. Operational burden
6. Compliance impact
7. Time to deliver
8. Long term maintainability
9. Reversibility
10. Recommendation

Make assumptions explicit. Identify where engineering input is required. Do not create a final decision if the context is insufficient.

Context:
[paste sanitized context]
```

## Expected output

- Options comparison table
- Recommendation
- Assumptions
- Engineering questions
- Decision needed

## Human review checklist

- Engineering validates technical claims
- Security validates risk claims
- Product validates customer impact
- Compliance validates regulatory claims
- Decision owner is clear

## Data handling notes

Avoid including proprietary architecture, source code, vulnerability details, or restricted system diagrams in unapproved tools.
