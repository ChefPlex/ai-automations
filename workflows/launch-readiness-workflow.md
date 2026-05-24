# Launch Readiness Workflow

## Goal

Prepare for a launch decision by confirming readiness across product, engineering, security, reliability, support, communications, documentation, monitoring, and rollback.

## Source systems

- Jira for launch scope and engineering readiness
- Google Docs for launch plan
- Google Sheets for readiness tracker
- Slack for open blockers
- Salesforce for customer impact, if applicable

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

- Remove unreleased product details if tool is not approved
- Remove customer names unless approved
- Remove restricted security and architecture details
- Do not include sensitive launch dependencies in unapproved tools

## Prompt sequence

1. Use `prompts/senior-tpm/dependency-map.md` to identify launch dependencies.
2. Use `prompts/senior-tpm/risk-burndown-plan.md` for top risks.
3. Use `prompts/senior-tpm/launch-readiness-review.md` for readiness output.
4. Use `prompts/senior-tpm/decision-memo.md` for final go or no go decision support.

## Final prompt

```text
You are helping me prepare a launch readiness review.

Using the sanitized context below, create:
1. Launch summary
2. Readiness by workstream
3. Open blockers
4. Top risks and mitigations
5. Rollback readiness
6. Monitoring readiness
7. Customer and support readiness
8. Missing evidence
9. Go, No Go, or Conditional Go recommendation
10. Decision owner and deadline

Do not recommend Go if critical evidence is missing.

Context:
[paste sanitized context]
```

## Human review checklist

- Engineering readiness confirmed
- Security readiness confirmed
- Reliability readiness confirmed
- Support readiness confirmed
- Documentation published
- Monitoring validated
- Rollback tested or accepted by decision owner
- Decision owner signs off

## Output artifacts

- Launch readiness checklist
- Go or no go decision memo
- Slack launch status update
- Jira readiness updates
- Post launch validation checklist

## Systems to update

- Jira launch epic
- Google Sheets readiness tracker
- Slack launch channel
- Program RAID log
- Launch approval record
