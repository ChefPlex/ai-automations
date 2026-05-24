# Jira Prompt Pack

Jira is the execution system, not the whole story. These prompts help translate Jira details into cleaner TPM views without losing the connection back to the source of record.

## Epic Quality Review

```text
Review the sanitized Jira epic below as a senior TPM.

Evaluate whether the epic has:
1. Clear business objective
2. Clear customer impact
3. Defined scope
4. Non-goals
5. Acceptance criteria
6. Milestones
7. Linked dependencies
8. Linked risks
9. Owners
10. Target dates
11. Rollout plan
12. Validation plan

Return recommended edits and missing fields. Do not invent missing details.

Jira epic:
[paste sanitized epic]
```

## Jira Roadmap Summary

```text
Create a roadmap summary from the sanitized Jira epics and stories below.

Group work into:
1. Now
2. Next
3. Later

For each group, include:
1. Major outcomes
2. Key epics
3. Engineering teams
4. Dependencies
5. Risks
6. Customer or business value
7. Leadership questions

Do not just list tickets. Translate the work into outcomes.

Jira data:
[paste sanitized Jira export]
```

## Jira to Executive Translation

```text
Translate the sanitized Jira details below into an executive update.

Explain the work as outcomes, not ticket counts.

Include:
1. Outcome we are working toward
2. Progress made
3. What remains
4. Where we are blocked
5. What risk exists
6. What decision is needed
7. Missing information

Keep it clear enough for a leader who will not read the tickets.

Jira details:
[paste sanitized Jira data]
```

## Sprint Risk Review

```text
Review the sanitized Jira sprint data below and identify sprint risk.

Look for:
1. Work at risk
2. Tickets with unclear ownership
3. Tickets that are too large
4. Tickets likely to slip
5. Dependencies not reflected in Jira
6. Scope that may not align to the milestone
7. Recommended actions before sprint close

Jira data:
[paste sanitized sprint data]
```

## Review before updating Jira

- Confirm ticket status with owners when needed
- Do not use AI output as the only source of truth
- Add missing dates, owners, blockers, and dependencies back into Jira
- Keep Jira comments factual and short
- Link final artifacts only when the team is allowed to see them
