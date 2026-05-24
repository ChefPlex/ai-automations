# Customer Escalation Workflow

## Goal

Create a clear, accurate, and constructive escalation brief when customer signals indicate program risk or urgency.

## Source systems

- Salesforce for account, case, opportunity, support, and customer context
- Jira for technical work status
- Slack for internal discussions
- Google Docs for escalation notes or action plans

## Inputs to gather

- Customer or anonymized segment
- Issue summary
- Business impact
- Technical impact
- Affected capability
- Current owner
- Mitigation
- Long term fix
- Timeline
- Open decisions

## Safety checks

Before prompting:

- Remove customer names if tool approval is unclear
- Remove contact names and email addresses
- Remove commercial terms unless approved
- Remove customer quotes unless approved
- Remove restricted security details
- Use minimum necessary context

## Prompt sequence

1. Use `prompts/tools/salesforce.md` for customer signal summary.
2. Use `prompts/tools/jira.md` for execution status.
3. Use `prompts/senior-tpm/escalation-draft.md` for the escalation.
4. Use `prompts/senior-tpm/decision-memo.md` if a leadership decision is required.

## Final prompt

```text
You are a senior TPM preparing a customer escalation brief.

Using the sanitized context below, create:
1. Escalation summary
2. Customer or segment impact
3. Current technical status
4. Current mitigation
5. Long term fix
6. Key risks
7. Decision or support needed
8. Proposed owner and next action
9. Customer communication recommendation

Do not overstate revenue, legal, security, or customer impact. Separate facts from assumptions.

Context:
[paste sanitized context]
```

## Human review checklist

- Validate customer impact with Sales, Support, or Customer Success
- Validate technical status with Engineering
- Validate customer communication with the approved owner
- Validate legal or commercial language if relevant
- Confirm executive ask and deadline

## Output artifacts

- Escalation brief
- Slack alignment message
- Jira blocker update
- Customer response prep notes
- Executive decision memo, if needed

## Systems to update

- Salesforce case or account notes, if appropriate
- Jira epic or blocker issue
- Program RAID log
- Google Doc escalation tracker
