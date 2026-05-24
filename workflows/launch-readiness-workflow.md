# Launch Readiness Workflow

## Goal

Prepare for a launch decision by confirming readiness across product, engineering, security, reliability, support, communications, documentation, monitoring, and rollback.

## Source systems

- Jira for launch scope and engineering readiness
- Google Docs for launch plan
- Google Sheets for readiness tracker
- Slack for open blockers
- Salesforce for customer impact, if applicable and approved

## Inputs to gather

- Launch scope
- Launch date
- Feature or platform change summary
- Engineering readiness
- Security readiness
- Reliability readiness
- Support readiness
- Documentation status
- Customer communication plan
- Monitoring and alerting status
- Rollback plan
- Known risks

## Safety checks

Before prompting:

- Remove unreleased product details unless approved
- Remove customer names and communication details unless approved
- Remove sensitive security or architecture details
- Confirm launch materials are approved for the AI tool
- Use roles instead of names when possible

## Prompt sequence

1. Use `prompts/senior-tpm/launch-readiness-review.md` to create the readiness view.
2. Use `prompts/senior-tpm/risk-burndown-plan.md` for open launch risks.
3. Use `prompts/tools/slack.md` to draft blocker follow-ups if needed.
4. Review with engineering, security, support, and product owners before the decision meeting.

## Final prompt

```text
Help me prepare a launch readiness review using the sanitized context below.

Create:
1. Readiness status by area
2. Open blockers
3. Top risks
4. Decision criteria
5. Go, no go, or conditional go recommendation
6. Required actions before launch
7. Missing information

Do not recommend go unless the evidence supports it. If a readiness area is unknown, mark it unknown.

Context:
[paste sanitized combined context]
```

## Human review checklist

- Readiness status is evidence-based
- Unknowns are not treated as green
- Rollback is validated or clearly not validated
- Security and support readiness are confirmed
- The decision criteria are clear

## Output artifacts

- Launch readiness doc
- Go or no go recommendation
- Blocker follow-up messages
- Jira updates
- Risk log updates

## Systems to update

- Jira launch epic
- Readiness tracker
- Program doc
- Slack launch channel
- RAID log

## Done when

The decision owner has enough evidence to make the launch call, and every conditional action has an owner and due date.
