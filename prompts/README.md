# Prompts

This directory contains reusable TPM prompts organized by level and workflow.

The prompts are meant to help with the messy middle of TPM work: turning scattered context into a clear artifact that names status, risk, ownership, and the next decision.

## Categories

- `junior-tpm`: Execution hygiene, action items, status, Jira cleanup, Slack summaries
- `senior-tpm`: Executive updates, decisions, escalations, launch readiness, risk, tradeoffs
- `director-review`: Artifact review, strategy review, operating models, metrics, and coaching prompts
- `tools`: Google Workspace, Slack, Salesforce, and Jira specific prompt packs

## How to use

1. Start with `standard-context-block.md`.
2. Choose the prompt that matches the work.
3. Paste only sanitized and approved context.
4. Ask the model to separate facts, assumptions, questions, and recommendations.
5. Review the output before publishing.
6. Update the system of record when the final artifact is complete.

## Recommended prompt wrapper

```text
Use only the context provided. Do not invent missing facts. Separate facts, assumptions, open questions, and recommendations. Identify the information I should confirm before sending this to the audience.
```

That wrapper is boring on purpose. It keeps the model from sounding more certain than the source material allows.
