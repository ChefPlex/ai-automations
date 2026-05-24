# Jira Hygiene Review Prompt

## Purpose

Review Jira issues for missing ownership, unclear acceptance criteria, stale work, blocked work, and dependency gaps.

## Best used for

- Sprint planning
- Program milestone reviews
- Pre executive review cleanup
- Jira epic quality checks

## Inputs

- Jira issue export
- Epic summary
- Ticket status
- Owners
- Due dates
- Dependencies

## Prompt

```text
You are a TPM reviewing Jira hygiene for a program.

Analyze the Jira issues below and identify:
1. Tickets missing owners
2. Tickets missing due dates
3. Tickets with unclear acceptance criteria
4. Tickets that appear stale
5. Tickets that are blocked but not marked blocked
6. Tickets that may belong under a different epic
7. Tickets that need dependency links
8. Suggested cleanup actions

Return the output as a table with:
Issue, Problem, Why It Matters, Recommended Fix, Owner Question.

Do not infer missing information. Mark unclear fields as "Needs confirmation."

Jira data:
[paste sanitized Jira export or ticket summaries]
```

## Expected output

A Jira cleanup table with recommended actions.

## Human review checklist

- Validate issue status in Jira
- Confirm due dates with engineering owners
- Confirm dependency links
- Update Jira directly after review
- Do not use AI output as the system of record

## Data handling notes

Remove internal URLs, customer identifiers, restricted vulnerability details, and sensitive architecture details before prompting.
