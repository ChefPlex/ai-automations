# Weekly Status Workflow

## Goal

Create a weekly program status update that is accurate, concise, and useful for stakeholders. The update should show what changed, what is at risk, and what decision or help is needed next.

## Source systems

- Jira for execution status
- Slack for blockers and decisions
- Google Docs for meeting notes and program plans
- Google Sheets for trackers or metrics
- Salesforce for customer signals, if relevant and approved

## Inputs to gather

- Current milestone
- Jira epic or sprint status
- Completed work
- Work in progress
- Blockers
- Risks
- Decisions needed
- Customer or business impact
- Upcoming milestones

## Safety checks

Before prompting:

- Remove customer names unless approved
- Remove internal links if unnecessary
- Remove sensitive security or incident details
- Remove commercial or renewal details unless approved
- Replace people names with roles when names are not needed

## Prompt sequence

1. Use `prompts/tools/jira.md` to translate Jira work into outcomes.
2. Use `prompts/junior-tpm/slack-thread-summary.md` for blocker threads.
3. Use `prompts/tools/salesforce.md` for customer signals if approved.
4. Use `prompts/senior-tpm/executive-program-update.md` for the final update.

## Final prompt

```text
Help me prepare a weekly executive status update using the sanitized combined context below.

Create:

1. Program health as Green, Yellow, or Red
2. One paragraph summary
3. What changed this week
4. Progress against milestones
5. Risks and blockers
6. Decisions needed
7. Next week focus
8. Missing information

Do not overstate progress. Separate facts from assumptions. Keep the output concise and useful.

Context:

[paste sanitized combined context]
```

## Example

See:

- [Weekly status source input](../examples/weekly-status-source-input.md)
- [Processed weekly status output](../examples/processed-weekly-status-output.md)

These examples show the expected conversion from scattered Jira, Slack, RAID, and meeting-note signal into a status update someone can actually act on.

## Human review checklist

- Health color matches the evidence
- Risks are clear and owned
- Blockers are specific
- Dates are accurate
- Customer or business impacts are approved for the audience
- Decision ask is clear
- Systems of record match the message

## Output artifacts

- Slack update
- Google Doc status section
- Executive email or review note
- Jira updates for blockers and dates

## Systems to update

- Jira epic status
- RAID log
- Slack program channel
- Google Doc program tracker
- Salesforce notes only if customer-facing follow-up is needed and approved

## Where this fails

This workflow works only as well as the source material. If Jira is stale, Slack has unconfirmed opinions, or the actual risk lives in side conversations, the generated update can look clean while missing the real problem.

Do not let the status draft become the system of record. Use it to write the update, then make sure Jira, the RAID log, and the program tracker agree with what you are about to publish.

## Done when

The update is published, owners know their next actions, and the systems of record match the message.
