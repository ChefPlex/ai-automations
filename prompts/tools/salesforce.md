# Salesforce Prompt Pack

Salesforce carries customer and business signal. Treat it carefully.

Use these prompts only with approved, sanitized context. Most of the time, the model does not need the customer name, exact revenue, renewal date, contract language, or account notes to help a TPM understand the program implication.

## Customer Signal Summary

```text
Use the sanitized Salesforce context below to summarize customer signals for a program review.

Return:
1. Customer names only if approved, otherwise anonymized segments
2. Common pain points
3. Revenue or renewal relevance, only if available and approved for use
4. Product or platform capability involved
5. Severity
6. Trend across customers
7. Recommended program action
8. Questions for Sales, Support, or Customer Success

Do not overstate revenue risk. Separate confirmed facts from assumptions.

Salesforce context:
[paste sanitized context]
```

## Customer Escalation Brief

```text
Create a customer escalation brief from the sanitized context below.

Include:
1. Customer or anonymized segment
2. Account context, only if approved
3. Issue summary
4. Business impact
5. Technical impact
6. Current owner
7. Current mitigation
8. Long-term fix
9. Timeline
10. Risks
11. Executive ask
12. Customer communication recommendation

Keep the brief factual. Do not create commitments that have not been approved.

Context:
[paste sanitized Salesforce and program context]
```

## Connect Program Work to Business Risk

```text
Use the sanitized Salesforce context below to connect platform work to business impact.

Identify:
1. Customers or segments impacted
2. Whether this relates to opportunities, renewals, escalations, or support cases
3. Likely business risk, only if supported by the context
4. How the program reduces that risk
5. Metric that could show impact
6. How to explain this to executives without overstating the data

Context:
[paste sanitized context]
```

## Customer Theme Detection

```text
Review the sanitized Salesforce notes below and identify recurring themes.

Group themes by:
1. Security
2. Reliability
3. Performance
4. Compliance
5. Product gap
6. Support experience
7. Documentation
8. Adoption blocker

For each theme, include supporting examples, affected segment, recommended owner, and program implication.

Salesforce notes:
[paste sanitized notes]
```

## Review before publishing

- Confirm Salesforce data is approved for the AI tool
- Remove customer names unless approved
- Remove revenue, renewal, contract, and commercial details unless approved
- Do not create customer commitments
- Validate conclusions with Sales, Support, Customer Success, Product, or Engineering as needed
