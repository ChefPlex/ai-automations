# Weekly Status Workflow

## Goal

Create a weekly program status update that is accurate, concise, and useful for stakeholders.

## Source systems

- Jira for execution status
- Slack for blockers and decisions
- Google Docs for meeting notes and program plans
- Google Sheets for trackers or metrics
- Salesforce for customer signals, if relevant

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
- Replace people names with roles if names are not needed

## Prompt sequence

1. Use `prompts/tools/jira.md` to translate Jira work into outcomes.
2. Use `prompts/junior-tpm/slack-thread-summary.md` for blocker threads.
3. Use `prompts/tools/salesforce.md` for customer signals.
4. Use `prompts/senior-tpm/executive-program-update.md` for the final update.

## Final prompt

```text
You are acting as a senior TPM preparing a weekly executive status update.

Use the sanitized context below and create:
1. Program health as Green, Yellow, or Red
2. One paragraph executive summary
3. What changed this week
4. Progress against milestones
5. Risks and blockers
6. Decisions needed
7. Next week focus
8. Missing information

Do not overstate progress. Separate facts from assumptions. Keep the output concise.

Context:
[paste sanitized combined context]
```

## Human review checklist

- Does the health color match the evidence?
- Are risks clear and owned?
- Are blockers actionable?
- Are dates accurate?
- Are customer or business impacts approved for the audience?
- Is the decision ask clear?

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
- Salesforce notes, only if customer facing follow up is needed and approved
