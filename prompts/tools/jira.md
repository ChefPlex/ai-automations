# Jira Prompt Pack

Prompts for Jira epic review, roadmap summaries, executive translation, and sprint risk review.

## Epic Quality Review

```text
You are reviewing a Jira epic as a senior TPM.

Evaluate whether the epic has:
1. Clear business objective
2. Clear customer impact
3. Defined scope
4. Non goals
5. Acceptance criteria
6. Milestones
7. Linked dependencies
8. Linked risks
9. Owners
10. Target dates
11. Rollout plan
12. Validation plan

Return recommended edits and missing fields.

Jira epic:
[paste sanitized epic]
```

## Jira Roadmap Summary

```text
Create a roadmap summary from these Jira epics and stories.

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

Jira data:
[paste sanitized Jira export]
```

## Jira to Executive Translation

```text
Translate the following Jira details into an executive ready update.

Do not list tickets. Explain the work as outcomes.

Include:
1. What outcome we are driving
2. What progress has been made
3. What remains
4. Where we are blocked
5. What risk exists
6. What decision is needed

Jira details:
[paste sanitized Jira data]
```

## Sprint Risk Review

```text
You are helping me review sprint risk.

Analyze the following Jira sprint data and identify:
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

## Data handling notes

Jira is a system of record. AI output should be reviewed and then reflected back in Jira. Remove restricted system details, customer identifiers, vulnerability details, and internal links unless approved.
