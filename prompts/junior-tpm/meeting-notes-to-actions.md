# Meeting Notes to Action Items Prompt

## Purpose

Turn raw meeting notes into structured decisions, action items, owners, and follow ups.

## Best used for

- Program syncs
- Design reviews
- Launch readiness meetings
- Escalation meetings
- Stakeholder alignment sessions

## Inputs

- Raw meeting notes
- Attendee list, if approved
- Program context
- Due dates mentioned
- Decisions discussed

## Prompt

```text
You are helping a junior TPM turn raw meeting notes into an action plan.

Extract:
1. Decisions made
2. Open questions
3. Action items
4. Owners
5. Due dates
6. Risks raised
7. Follow up meetings needed
8. Items that need confirmation because the notes are unclear

Write the action items in a format I can paste into Slack and Jira.

Do not invent owners or due dates. If an owner or due date is unclear, mark it as "Needs confirmation."

Meeting notes:
[paste sanitized notes]
```

## Expected output

- Decisions
- Action items
- Open questions
- Risks
- Follow up meetings
- Confirmation needed

## Human review checklist

- Confirm each owner
- Confirm each date
- Confirm that decisions were actually made
- Remove informal or sensitive comments
- Update Jira and Slack after review

## Data handling notes

Remove names, confidential statements, customer details, and sensitive security information unless approved for the AI tool.
