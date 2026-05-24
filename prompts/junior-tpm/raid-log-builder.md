# RAID Log Builder Prompt

## Purpose

Convert scattered program notes into a RAID log covering risks, assumptions, issues, and dependencies.

## Best used for

- Program planning
- Weekly status preparation
- Executive review preparation
- Milestone risk review

## Inputs

- Program notes
- Jira data
- Slack updates
- Meeting notes
- Known blockers
- Current milestone

## Prompt

```text
You are a TPM creating a RAID log.

From the context below, identify:
1. Risks
2. Assumptions
3. Issues
4. Dependencies

For each item, include:
Description, Impact, Owner, Due Date, Mitigation, Status, and Escalation Needed.

Separate facts from assumptions. Do not invent owners or due dates. Mark unclear fields as "Needs confirmation."

Context:
[paste sanitized notes, Jira data, Slack updates, or planning doc]
```

## Expected output

A RAID log table.

## Human review checklist

- Validate risks with stakeholders
- Confirm owners and dates
- Escalate only after checking with owners
- Update the official RAID log after review

## Data handling notes

Remove customer names, sensitive system names, and restricted risk details before prompting.
