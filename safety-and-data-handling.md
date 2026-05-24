# Safety and Data Handling

This guide explains how to use AI prompts safely in a TPM environment involving Google Workspace, Slack, Salesforce, and Jira.

Always follow your company's approved AI usage, data classification, security, privacy, legal, and customer communication policies.

## Golden rule

Only paste data into an AI tool when you are allowed to use that tool for that data.

When uncertain, remove the data or ask the appropriate internal owner before using it.

## Do not paste into unapproved AI tools

Do not paste:

- Passwords, API keys, tokens, secrets, certificates, private keys, or credentials
- Customer names, contacts, contract terms, renewal dates, account notes, or commercial terms
- Personal data, employee data, health data, payment data, or regulated data
- Production logs with identifiers
- Vulnerability details, exploit details, or sensitive architecture details
- Legal privileged content
- Unreleased product plans or roadmap commitments
- Source code or proprietary implementation details without approval
- Incident details that require restricted handling
- Screenshots containing sensitive metadata
- Slack threads that include confidential or personal information

## Safer substitution patterns

Use substitutions before prompting.

| Sensitive item | Safer replacement |
|---|---|
| Customer name | Customer A, Customer B, Strategic Customer 1 |
| Employee name | Engineer A, Product Lead B, Support Owner C |
| Account value | High ARR account, renewal risk, enterprise segment |
| Jira link | Jira Epic 1, Jira Story 2 |
| Service name | Service A, Payment Service, Identity Service |
| Vulnerability ID | Critical vulnerability, auth bypass risk, encryption gap |
| Specific deadline | Date A, Q3 milestone, regulatory deadline |
| Slack channel | Program channel, engineering channel |

## Prompting with Salesforce data

Salesforce often contains customer, commercial, renewal, support, and escalation details. Treat it carefully.

Before using Salesforce content:

- Remove customer names unless the tool is approved for that data
- Remove contact names and email addresses
- Remove contract terms and commercial amounts unless approved
- Replace opportunity names with generic labels
- Summarize sensitive details instead of pasting raw notes
- Remove support case IDs if they identify customers
- Keep only the minimum context needed for the TPM task

## Prompting with Slack data

Slack threads can include sensitive, informal, or incomplete information.

Before using Slack content:

- Remove names if not needed
- Remove confidential channel names
- Remove screenshots
- Remove incident details if restricted
- Remove secrets, logs, links, and pasted code
- Do not treat Slack opinions as facts
- Ask AI to separate facts from assumptions

## Prompting with Jira data

Jira is often safer than raw Slack, but it can still contain sensitive details.

Before using Jira content:

- Remove customer identifiers
- Remove security details that are not approved for AI tools
- Remove links to internal systems if unnecessary
- Preserve owners, status, due dates, and dependencies only when allowed
- Validate AI outputs against Jira before publishing

## Prompting with Google Workspace data

Google Docs, Sheets, and Slides may contain executive, customer, legal, roadmap, or security sensitive content.

Before using Google Workspace content:

- Confirm the document classification
- Remove sensitive comments and suggestions
- Remove raw customer quotes unless approved
- Remove restricted roadmap details
- Remove legal and compliance review content unless approved
- Paste only the section needed for the task

## Human review checklist

Before sending AI assisted output, confirm:

- Dates are accurate
- Owners are accurate
- Jira status is accurate
- Customer impact is not overstated
- Revenue risk is not overstated
- Security risk is not understated
- Compliance language is approved
- Legal commitments are not created accidentally
- The decision ask is clear
- The tone is appropriate for the audience
- No sensitive data remains in the output

## Safe prompt pattern

```text
Use the sanitized context below. Do not infer customer names, revenue, legal obligations, or security severity beyond what is explicitly stated. Separate facts from assumptions. Identify missing information.

Context:
[paste sanitized context]
```

## Unsafe prompt pattern

```text
Here is the entire Slack thread, Salesforce account, Jira epic, customer contract, and incident report. Write an executive update.
```

This pattern creates unnecessary data exposure and is likely to produce inaccurate or overconfident output.

## When not to use AI

Do not use AI as the primary tool for:

- Legal advice
- Security vulnerability handling decisions
- Customer contractual commitments
- HR or performance management decisions
- Regulated data interpretation
- Incident commander decisions
- Final go or no go launch approval
- Final executive sign off

AI can help structure materials for review, but accountable humans must make and approve decisions.
