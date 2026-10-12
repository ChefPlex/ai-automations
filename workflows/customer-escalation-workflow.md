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
- Long-term fix
- Timeline
- Open decisions

## Safety checks

Before prompting:

- Confirm Salesforce content is approved for the AI tool
- Remove customer names, contacts, revenue, renewal, and contract details unless approved
- Remove internal links and sensitive technical details
- Do not paste raw account notes unless approved
- Use anonymized segments when names are not needed

## Prompt sequence

1. Use `prompts/tools/salesforce.md` to summarize the customer signal.
2. Use `prompts/tools/jira.md` to confirm execution status.
3. Use `prompts/senior-tpm/escalation-draft.md` to draft the escalation.
4. Review with the appropriate product, engineering, support, or customer owner before sending.

## Final prompt

```text
Help me create a customer escalation brief using the sanitized context below.

Include:
1. Customer or anonymized segment
2. Issue summary
3. Business impact
4. Technical impact
5. Current owner
6. Current mitigation
7. Long-term fix
8. Timeline
9. Risks
10. Decision or support needed
11. Recommended next step
12. Missing information

Keep it factual. Do not create customer commitments. Do not overstate revenue or renewal risk.

Context:
[paste sanitized combined context]
```

## Where this fails

This workflow pulls from three systems that rarely agree. Salesforce reflects what the customer said, Jira reflects what engineering logged, and Slack holds the part nobody wrote down. The brief will blend them into one story, and where they conflict it will usually pick one without saying so.

Check that the technical status matches what engineering says today, not what the ticket said last week. Have the account owner confirm the business impact, and make sure no date in the brief reads like a promise to the customer.

## Human review checklist

- Customer information is approved or anonymized
- Business impact is supported by source data
- No commitment is created accidentally
- Technical status matches Jira or engineering confirmation
- The ask is clear and owned

## Output artifacts

- Escalation brief
- Leadership Slack or email draft
- Customer communication recommendation
- Jira or RAID updates

## Systems to update

- Salesforce notes, only if approved and customer-facing follow-up is needed
- Jira blockers and owners
- RAID log
- Program status doc

## Done when

The escalation has a clear owner, a clear ask, an approved customer impact statement, and a date for the next checkpoint.
