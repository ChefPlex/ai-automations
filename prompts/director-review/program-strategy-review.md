# Program Strategy Review Prompt

## Use this when

A program plan needs a director-level challenge before it becomes the plan everyone starts executing.

## Why it matters

Plans usually look best before they meet dependencies. This review looks for weak goals, soft metrics, unclear owners, hidden risks, and timelines that rely on luck.

## Inputs to gather

- Program plan
- Goals
- Success metrics
- Scope
- Timeline
- Stakeholders
- Dependencies
- Risks
- Executive ask

## Prompt

```text
Review the sanitized program plan below as a director-level TPM.

Evaluate:
1. Whether the goal is clear
2. Whether success metrics are measurable
3. Whether the scope is realistic
4. Whether ownership is clear
5. Whether dependencies are understood
6. Whether risks are surfaced
7. Whether the timeline is credible
8. Whether the executive ask is clear
9. What is missing
10. What I should challenge before approving the plan

Return a concise review with strengths, concerns, questions, and recommended next steps.

Program plan:
[paste sanitized plan]
```

## Expected output

- Strengths
- Concerns
- Questions to ask
- Risks to challenge
- Recommended next steps

## Human review checklist

- Goals and metrics are tested
- Ownership gaps are visible
- Timeline risk is called out plainly
- Executive ask is clear
- Next steps are specific


## Data handling notes

Remove sensitive roadmap, customer, financial, security, and legal details unless approved.


## Done when

The review is ready when the program owner knows what to fix before the plan goes forward.
