# Salesforce Prompt Pack

Prompts for turning Salesforce account, case, opportunity, and customer signal data into TPM program insights.

## Customer Signal Summary

```text
You are helping me summarize Salesforce customer signals for a program review.

Analyze the following account, case, opportunity, or support notes.

Return:
1. Customer names or anonymized segments
2. Common pain points
3. Revenue or renewal relevance, if available and approved for use
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
Create a customer escalation brief.

Include:
1. Customer or anonymized customer segment
2. Account context
3. Issue summary
4. Business impact
5. Technical impact
6. Current owner
7. Current mitigation
8. Long term fix
9. Timeline
10. Risks
11. Executive ask
12. Customer communication recommendation

Context:
[paste sanitized Salesforce and program context]
```

## Connect Program Work to Revenue Risk

```text
You are helping me connect platform work to business impact.

Using the Salesforce context below, identify:
1. Which customers or segments are impacted
2. Whether this relates to open opportunities, renewals, escalations, or support cases
3. The likely business risk
4. How the program reduces that risk
5. What metric could show impact
6. How to explain this to executives without overstating the data

Context:
[paste sanitized Salesforce context]
```

## Customer Theme Detection

```text
Review these Salesforce notes and identify recurring themes.

Group the themes by:
1. Security
2. Reliability
3. Performance
4. Compliance
5. Product gap
6. Support experience
7. Documentation
8. Adoption blocker

For each theme, include supporting examples, affected customer segments, recommended owner, and program implication.

Salesforce notes:
[paste sanitized notes]
```

## Data handling notes

Salesforce can contain customer names, contacts, commercial terms, legal commitments, support history, renewal risk, and account strategy. Use only approved AI tools and sanitize context before prompting.
