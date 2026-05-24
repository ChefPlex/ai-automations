# Executive Review Workflow

## Goal

Prepare a concise executive review that focuses on outcomes, risks, decisions, and leadership asks.

## Source systems

- Jira for delivery status
- Google Docs for program plan
- Google Sheets for metrics
- Google Slides for readout
- Slack for blockers and decision history
- Salesforce for customer signals, if relevant and approved

## Inputs to gather

- Program objective
- Strategic reason
- Current status
- Milestones
- Metrics
- Top risks
- Decisions needed
- Leadership asks
- Customer or business impact
- Recommendation

## Safety checks

Before prompting:

- Remove sensitive customer, commercial, security, legal, and roadmap details unless approved
- Confirm metrics are approved for the audience
- Use sanitized summaries instead of raw Slack or Salesforce data
- Separate facts from assumptions

## Prompt sequence

1. Use `prompts/senior-tpm/executive-program-update.md` to draft the narrative.
2. Use `prompts/director-review/artifact-critique.md` to review the artifact.
3. Use `prompts/tools/google-workspace.md` to shape the slides or doc.
4. Validate with program owners before sending to leadership.

## Final prompt

```text
Help me prepare an executive review using the sanitized context below.

Create:
1. One paragraph summary
2. Why this program matters now
3. Current status
4. Progress against milestones
5. Metrics that matter
6. Top risks and mitigations
7. Decisions needed
8. Recommendation
9. Leadership asks
10. Missing information

Keep the message clear, direct, and decision-oriented. Do not bury the ask.

Context:
[paste sanitized context]
```

## Human review checklist

- Summary leads with the main point
- Metrics are accurate and approved
- Risks are specific
- Decision ask is obvious
- Recommendation is supported by evidence
- No sensitive data remains

## Output artifacts

- Executive review doc
- Google Slides outline
- Leadership email or Slack summary
- Decision log update
- RAID updates

## Systems to update

- Program doc
- Decision log
- Jira
- RAID log
- Slack channel after review

## Done when

Leadership has a clear readout, the decision is captured, and the systems of record reflect what changed.
