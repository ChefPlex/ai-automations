# Standard Context Block

Use this block before most prompts in this repo.

The model does better when the TPM gives it the same context a human reviewer would need: what program this is, why it matters, what systems are involved, what is known, what is blocked, and what decision is needed.

```text
Program:
Business goal:
Customer impact:
Current phase:
Critical milestone:
Target date:
Engineering teams involved:
Product teams involved:
Security, compliance, or legal dependencies:
Jira epic or project:
Relevant Slack context:
Relevant Google Docs, Sheets, or Slides:
Relevant Salesforce accounts, cases, opportunities, or customer signals:
Known risks:
Known blockers:
Decision needed:
Audience:
Output format:
Facts already confirmed:
Assumptions to validate:
Information that must not be inferred:
```

## Notes

Use only the fields that matter for the task. Leaving a field blank is better than making something up.

Before prompting, remove or anonymize anything the tool is not approved to process. That includes customer names, account details, security details, internal links, commercial terms, personal data, secrets, and restricted incident content.

## Useful wrapper

```text
Use only the context provided. Separate facts, assumptions, open questions, and recommendations. Do not invent missing facts. If the context is not enough to support a conclusion, say what is missing and why it matters.
```

That wrapper saves a lot of cleanup later.
