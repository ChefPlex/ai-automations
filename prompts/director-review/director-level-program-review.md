# Director-Level Program Review Prompt

## Use this when

A senior TPM program needs a broad health check across strategy, execution, risk, metrics, and communication.

## Why it matters

Director review should help the TPM see around corners. The goal is not to nitpick. The goal is to find the few things that will matter most to delivery, trust, and leadership confidence.

## Inputs to gather

- Program context
- Status update
- Plan
- Metrics
- Risks
- Dependencies
- Recent decisions
- Audience

## Prompt

```text
Review the sanitized program material below as a director-level TPM.

Assess the program across:
1. Strategy
2. Execution
3. Cross-functional coordination
4. Technical depth
5. Risk management
6. Metrics
7. Customer impact
8. Executive communication
9. Operational readiness
10. Decision quality

Return:
1. Strengths
2. Concerns
3. Questions to ask
4. Recommendations
5. Leadership review readiness: the evidence that it is ready, the evidence
   that it is not, and the items still missing. Do not give a verdict. Whether
   it goes to leadership is the TPM's decision.

Be direct and practical. Do not over-polish weak areas.

Context:
[paste sanitized program context]
```

## Expected output

- Strengths
- Concerns
- Questions
- Recommendations
- Evidence for and against leadership readiness, and what is missing

## Where this fails

This review is only as good as the material pasted in. It cannot see the hallway conversations, the politics around the program, or the history behind a decision, so it will flag things the team already settled and miss the risk nobody wrote down.

Treat its concerns as questions for the program owner. A concern is not a finding until someone with context confirms it, and a quiet section in the review does not mean that area is healthy.

## Human review checklist

- Feedback is specific
- Risks are tied to impact
- Recommendations are practical
- The readiness decision is made by the TPM from the evidence, not taken from the model
- Missing information is explicit


## Data handling notes

Remove restricted program, customer, security, legal, and commercial information before prompting.


## Done when

The review is ready when the TPM knows what to keep, what to fix, and what to escalate.
