# Executive Program Update Prompt

## Purpose

Convert program inputs from Jira, Slack, Salesforce, Google Docs, and meeting notes into a concise executive update.

## Best used for

- VP level weekly updates
- Steering committee reviews
- Program health reviews
- Executive Slack updates
- Leadership prep

## Inputs

- Program objective
- Current milestone
- Jira epic or sprint summary
- Slack blocker threads
- Salesforce customer signals
- RAID log updates
- Decisions needed
- Target audience

## Prompt

```text
You are acting as a senior Technical Program Manager preparing an executive program update.

Using the sanitized context below, create an update with:
1. Overall status as Green, Yellow, or Red
2. One paragraph executive summary
3. What changed since the last update
4. Progress against milestones
5. Customer or business impact
6. Top risks with owner, mitigation, and escalation threshold
7. Blockers requiring leadership help
8. Decisions needed this week
9. Recommended next action

Use concise, executive ready language. Do not overstate progress. Separate facts from assumptions. Identify missing information.

Context:
[paste sanitized context]
```

## Expected output

- Executive summary
- Status color with rationale
- Key updates
- Risks and blockers
- Decisions needed
- Recommended next action
- Missing information

## Human review checklist

- Are customer names removed or approved for use?
- Are security details sanitized?
- Are dates and owners accurate?
- Are risks stated clearly?
- Is the executive ask obvious?
- Does the status color match the facts?

## Data handling notes

Be especially careful with customer signals, security risks, and revenue impact. Avoid overstating impact if the source data is incomplete.
