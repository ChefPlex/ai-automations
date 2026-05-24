# Compliance Intake Workflow

## Goal

Translate compliance, audit, policy, or control requests into clear engineering work with owners, evidence needs, milestones, and risk visibility.

## Source systems

- Compliance request tracker
- Jira
- Google Docs
- Slack
- Evidence repositories
- Salesforce only if customer commitments are relevant and approved

## Inputs to gather

- Compliance requirement or control
- Deadline
- Evidence requested
- Systems or services in scope
- Engineering owners
- Current state
- Gaps
- Risk of non-completion
- Review or approval owners

## Safety checks

Before prompting:

- Do not paste legal privileged content unless approved
- Remove customer commitments unless approved
- Remove sensitive architecture or control details unless approved
- Confirm evidence handling rules
- Use summaries instead of raw evidence when possible

## Prompt sequence

1. Summarize the compliance request in plain language.
2. Use `prompts/junior-tpm/acceptance-criteria-builder.md` to turn the request into Jira-ready work.
3. Use `prompts/senior-tpm/dependency-map.md` to identify service and evidence dependencies.
4. Use `prompts/senior-tpm/risk-burndown-plan.md` for deadline risk.
5. Review with compliance, security, legal, and engineering owners as needed.

## Final prompt

```text
Help me translate the sanitized compliance request below into an engineering execution plan.

Create:
1. Plain-language requirement summary
2. Systems or services in scope
3. Evidence needed
4. Engineering work items
5. Owners
6. Milestones
7. Dependencies
8. Risks
9. Approval path
10. Missing information

Do not provide legal advice. Do not invent compliance obligations. Mark anything that needs compliance, legal, or security confirmation.

Context:
[paste sanitized context]
```

## Human review checklist

- Requirement is translated accurately
- Legal or compliance interpretation is not invented
- Evidence needs are clear
- Engineering work has owners
- Risks and deadlines are visible

## Output artifacts

- Compliance intake summary
- Jira epics or stories
- Evidence tracker
- RAID log entries
- Approval path summary

## Systems to update

- Compliance tracker
- Jira
- Evidence repository
- Program doc
- Slack channel for approved follow-up

## Done when

The request has been translated into owned work, evidence needs are understood, and any interpretation questions are routed to the right owner.
