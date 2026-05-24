# Weekly Status Update Prompt

## Purpose

Convert raw Jira updates, Slack threads, meeting notes, and program context into a concise weekly status update.

## Best used for

- Weekly program updates
- Team level updates
- Manager updates
- Program health summaries

## Inputs

- Jira epic or sprint summary
- Slack blocker updates
- Meeting notes
- Current milestone
- Known risks
- Decisions needed

## Prompt

```text
You are helping me act as a junior TPM creating a weekly program status update.

Review the Jira summaries, Slack updates, meeting notes, and program context below.

Create a concise weekly status update with:
1. Overall program health as Green, Yellow, or Red
2. What changed since last week
3. Completed work
4. In progress work
5. Blockers
6. Risks
7. Decisions needed
8. Next steps for the coming week

Use clear, neutral, executive ready language. Do not exaggerate progress. Separate facts from assumptions. Call out missing information separately.

Context:
[paste sanitized context]
```

## Expected output

- Program health
- Summary paragraph
- Completed work
- In progress work
- Risks and blockers
- Decisions needed
- Next steps
- Missing information

## Human review checklist

- Are dates accurate?
- Are owners accurate?
- Is program health justified?
- Are blockers stated clearly?
- Are decisions assigned to the right audience?
- Is any sensitive data exposed?

## Data handling notes

Sanitize customer names, Salesforce details, Slack names, Jira links, and sensitive technical details before prompting.
