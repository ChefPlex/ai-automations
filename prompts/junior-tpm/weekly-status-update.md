# Weekly Status Update Prompt

## Use this when

The raw inputs are spread across Jira, Slack, meeting notes, and maybe a tracker, and the team needs one clean weekly view.

## Why it matters

A weekly update should do more than list activity. It should show what changed, what is at risk, who owns the next step, and whether anyone needs to make a decision.

## Inputs to gather

- Program objective
- Current milestone
- Jira epic or sprint summary
- Slack blocker updates
- Meeting notes
- Known risks
- Known blockers
- Decisions needed

## Prompt

```text
Help me create a weekly program status update from the sanitized context below.

The update should make the following clear:
1. Overall program health as Green, Yellow, or Red
2. What changed since last week
3. Completed work
4. Work in progress
5. Blockers
6. Risks
7. Decisions needed
8. Next steps for the coming week
9. Missing information I should confirm

Keep the language plain and direct. Do not make the program sound healthier than the facts support. Separate confirmed facts from assumptions.

Context:
[paste sanitized context]
```

## Expected output

- Program health with rationale
- Short summary paragraph
- Completed work
- Work in progress
- Risks and blockers
- Decisions needed
- Next steps
- Missing information

## Human review checklist

- Dates are accurate
- Owners are accurate
- Program health is justified by evidence
- Blockers are stated clearly
- Decisions are assigned to the right audience
- Sensitive data has been removed


## Data handling notes

Sanitize customer names, Salesforce details, Slack names, Jira links, and sensitive technical details before prompting.


## Done when

The update is ready when a manager can read it in under two minutes and know what changed, what is at risk, and what needs attention next.
