# Artifact Critique Output

Fictional, sanitized example.

## Concise critique

The draft is too vague for a director-level review. It says the program is making progress, but it does not explain the actual risk: the schedule depends on Team B committing to a migration date and validation environment access being approved. It also hides a newly discovered observability dependency and an incomplete rollback review behind soft language.

The phrase "nothing looks blocked" is technically possible but not useful. The better framing is Yellow: not blocked yet, but at risk if the open items do not close this week.

## Stronger rewritten version

Project Atlas is Yellow for Q3 validation readiness. Migration testing is complete for 14 of 18 services, but the remaining path depends on two items closing this week: Team B committing to a migration date and validation environment access being confirmed.

There are two additional readiness gaps: an observability dependency was discovered this week and needs to be added to Jira and the RAID log, and the support rollback runbook is drafted but not yet reviewed.

No executive decision is required today. If Team B timing or validation access is still unresolved by next week, leadership should be prepared to decide whether to keep the current validation window or move to a contingency plan.

## Questions to answer before sending

- What date does Team B commit to for migration?
- When will validation environment access be approved?
- Who owns the rollback runbook review?
- Does the observability dependency affect validation evidence collection?
- What is the latest date leadership can decide on the validation window without creating downstream churn?

## Risks that may be underestimated

| Risk | Why it matters |
|---|---|
| Team B timing is still uncommitted | The remaining validation schedule may compress quickly. |
| Environment access is not confirmed | Evidence collection may slip even if migration work finishes. |
| Observability dependency is not tracked | Work can fall through the cracks if it stays out of Jira and RAID. |
| Rollback review is incomplete | Operational readiness may be weaker than the status implies. |

## Recommended next action

Send the stronger Yellow version after confirming whether Team B and the platform owner can commit to dates this week. Do not publish the original draft as Green or "tracking" without naming the schedule risk.
