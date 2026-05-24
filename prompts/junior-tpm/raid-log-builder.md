# RAID Log Builder Prompt

## Use this when

Program context is scattered and the TPM needs to separate risks, assumptions, issues, and dependencies.

## Why it matters

RAID logs are useful only when they make the next action visible. A long list of vague concerns is just a parking lot with columns.

## Inputs to gather

- Program notes
- Jira status
- Slack updates
- Meeting notes
- Known owners
- Target milestone

## Prompt

```text
Use the sanitized context below to build a RAID log.

Identify:
1. Risks
2. Assumptions
3. Issues
4. Dependencies

For each item, include Description, Impact, Owner, Due Date, Mitigation or Next Step, Status, and Escalation Needed.

Separate facts from assumptions. If an owner or date is missing, say so plainly.

Context:
[paste sanitized context]
```

## Expected output

- RAID table
- Top three items needing attention
- Missing owners or dates
- Escalation candidates

## Human review checklist

- Risks are future-looking
- Issues are current problems
- Assumptions are things to validate
- Dependencies name both sides of the handoff
- Every item has a next step or a missing field


## Data handling notes

Remove sensitive customer, security, commercial, and internal system details before prompting.


## Done when

The RAID log is ready when the highest-risk item has an owner, a mitigation, and a clear escalation point.
