# Safety and Data Handling

This guide explains how to use AI prompts safely in a TPM environment involving Google Workspace, Slack, Salesforce, and Jira.

Always follow your company's approved AI usage, data classification, security, privacy, legal, and customer communication policies. This file is practical guidance, not a substitute for those policies.

## Golden rule

Only paste data into an AI tool when you are allowed to use that tool for that data.

When uncertain, remove the data or ask the appropriate internal owner before using it. Not every useful prompt needs raw data. A clean summary is usually enough.

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

If that list feels long, good. It should. Most data handling problems start with someone pasting more context than the task required.

## Safer substitution patterns

Use placeholders that preserve meaning without carrying sensitive details.

| Sensitive source | Safer substitution |
|---|---|
| Customer name | Customer A, large financial services customer, public sector account |
| Account owner | Sales owner, Customer Success owner, Support lead |
| Revenue amount | High, medium, low business impact, or approved range |
| Internal service name | Service A, identity service, billing service, shared platform service |
| Vulnerability detail | Security finding, control gap, remediation item |
| Contract language | Customer commitment, renewal dependency, contractual concern |
| Person name | Engineering owner, product owner, compliance owner |

The goal is to keep enough signal to do the TPM work while removing details the model does not need.

## Prompting with Salesforce data

Salesforce can carry customer, commercial, renewal, support, legal, and relationship context. Treat it carefully.

Before using Salesforce content:

- Confirm the AI tool is approved for that data class
- Remove or anonymize customer names unless explicitly approved
- Remove contract terms, renewal dates, and revenue values unless approved
- Remove customer contacts and personal information
- Remove raw case comments if they contain sensitive details
- Preserve the business signal in a safe form

Safer pattern:

```text
A large enterprise customer in the healthcare segment has raised a support escalation tied to delayed delivery of Capability X. The account name, revenue value, and contract terms have been removed. The issue may affect renewal confidence if the milestone slips beyond Q3.
```

That gives enough context for a program update without carrying unnecessary detail.

## Prompting with Slack data

Slack is messy by design. It often contains side comments, incomplete facts, customer references, personal data, screenshots, internal links, and opinions stated as facts.

Before using Slack content:

- Summarize the thread instead of pasting the whole thing when possible
- Remove people names unless needed
- Remove customer names and internal links
- Remove screenshots
- Remove incident details if restricted
- Remove secrets, logs, links, and pasted code
- Do not treat Slack opinions as facts
- Ask the model to separate facts from assumptions

Slack is good for finding signals. It is not always good evidence by itself.

## Prompting with Jira data

Jira is often cleaner than raw Slack, but it can still contain sensitive details.

Before using Jira content:

- Remove customer identifiers
- Remove sensitive security details that are not approved for AI tools
- Remove internal links if they are not needed
- Preserve owners, status, due dates, and dependencies only when allowed
- Validate output against Jira before publishing

Jira should be used to ground status. If the model says something is complete but Jira does not, trust Jira until a human confirms otherwise.

## Prompting with Google Workspace data

Google Docs, Sheets, and Slides may contain executive, customer, legal, roadmap, or security-sensitive content.

Before using Google Workspace content:

- Confirm the document classification
- Remove sensitive comments and suggestions
- Remove raw customer quotes unless approved
- Remove restricted roadmap details
- Remove legal and compliance review content unless approved
- Paste only the section needed for the task

The full document is rarely needed. A focused excerpt usually produces a better answer anyway.

## Human review checklist

Before sending AI-assisted output, confirm:

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

This is the part where the TPM earns the update.

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

This pattern creates unnecessary data exposure and is likely to produce inaccurate or overconfident output. It also creates cleanup work nobody needed.

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

AI can help structure material for review. Accountable humans still make and approve the decisions.

PS: When the data is sensitive and the task is mostly judgment, talk to the right person instead of trying to prompt around the discomfort. Faster is not always safer.
