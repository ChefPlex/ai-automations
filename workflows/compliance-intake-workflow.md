# Compliance Intake Workflow

## Goal

Translate compliance, audit, policy, or control requests into clear engineering work with owners, evidence needs, milestones, and risk visibility.

## Source systems

- Compliance request tracker
- Jira
- Google Docs
- Slack
- Evidence repositories
- Salesforce, only if customer commitments are relevant and approved

## Inputs to gather

- Compliance requirement or control
- Deadline
- Evidence requested
- Systems or services in scope
- Engineering owners
- Current state
- Gaps
- Risk of non completion
- Review or approval owners

## Safety checks

Before prompting:

- Do not paste audit privileged or restricted legal content into unapproved tools
- Remove customer names unless approved
- Remove sensitive control details if restricted
- Remove internal evidence links
- Use summaries instead of raw evidence when possible

## Prompt sequence

1. Use `prompts/senior-tpm/dependency-map.md` to map teams and evidence dependencies.
2. Use `prompts/senior-tpm/risk-burndown-plan.md` for compliance deadline risk.
3. Use `prompts/junior-tpm/acceptance-criteria-builder.md` to turn requirements into Jira work.
4. Use `prompts/senior-tpm/executive-program-update.md` for leadership reporting.

## Final prompt

```text
You are a senior TPM translating a compliance request into an execution plan.

Using the sanitized context below, create:
1. Requirement summary
2. Scope
3. Non scope
4. Evidence needed
5. Engineering work required
6. Jira epics or stories to create
7. Owners
8. Milestones
9. Risks and mitigations
10. Open questions for Compliance, Legal, Security, or Engineering
11. Executive summary

Do not provide legal advice. Identify where review from Compliance, Legal, Security, or Privacy is required.

Context:
[paste sanitized context]
```

## Human review checklist

- Compliance validates requirement interpretation
- Engineering validates feasibility
- Security validates control details
- Legal or privacy validates regulated language if needed
- Jira work is created with clear acceptance criteria
- Evidence location is approved

## Output artifacts

- Compliance intake summary
- Jira epic and stories
- Evidence tracker
- RAID log entries
- Executive update

## Systems to update

- Compliance tracker
- Jira
- Google Sheets evidence tracker
- Google Docs program plan
- Slack program channel
