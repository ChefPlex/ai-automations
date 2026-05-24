# Program Standup Prep Prompt

## Purpose

Prepare a TPM to run a focused program standup.

## Best used for

- Weekly program standups
- Cross team execution checkpoints
- Milestone health checks
- Dependency reviews

## Inputs

- Current milestone
- Jira status
- Recent Slack updates
- RAID log
- Known blockers

## Prompt

```text
You are helping me prepare for a program standup.

Based on the context below, create:
1. The top five topics to cover
2. Questions to ask each team
3. Blockers to validate
4. Dependencies to confirm
5. Decisions needed
6. A suggested agenda
7. A short opening statement for the TPM

Keep the meeting focused on decisions, blockers, and next actions.

Context:
[paste sanitized program notes]
```

## Expected output

- Agenda
- Opening statement
- Team questions
- Blockers
- Decisions needed
- Follow up items

## Human review checklist

- Confirm attendees
- Confirm whether sensitive items should be discussed live
- Keep agenda realistic for the meeting length
- Make sure every topic has a desired outcome

## Data handling notes

Do not paste restricted incident, customer, or vulnerability details unless approved.
