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

- Remove sensitive customer and account details unless approved
- Remove confidential financial data unless approved
- Remove restricted roadmap, legal, security, or incident information unless approved
- Confirm intended audience

## Prompt sequence

1. Use `prompts/senior-tpm/executive-program-update.md` for current status.
2. Use `prompts/senior-tpm/decision-memo.md` for leadership decisions.
3. Use `prompts/director-review/artifact-critique.md` to improve the draft.
4. Use `prompts/tools/google-workspace.md` to create the slide outline.

## Final prompt

```text
You are a director level TPM preparing an executive review.

Using the sanitized context below, create:
1. Executive summary
2. Why this program matters now
3. Current status
4. Progress against milestones
5. Metrics and evidence
6. Top risks
7. Decisions needed
8. Recommendation
9. Leadership asks
10. Slide by slide outline for a concise review

Write for a VP or SVP audience. Keep the narrative clear, direct, and decision oriented.

Context:
[paste sanitized context]
```

## Human review checklist

- Executive ask is explicit
- Status is evidence based
- Metrics are accurate
- Risks are not hidden
- Decisions are assigned to the correct leaders
- Slide deck does not contain sensitive details outside the intended audience

## Output artifacts

- Executive summary
- Slide outline
- Decision memo
- Leadership ask list
- Updated RAID log

## Systems to update

- Google Slides deck
- Google Doc program plan
- Jira status
- RAID log
- Slack leadership update
