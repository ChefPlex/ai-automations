# Prompts

This directory contains reusable TPM prompts organized by level and workflow.

## Categories

- `junior-tpm`: Execution hygiene, action items, status, Jira cleanup, Slack summaries
- `senior-tpm`: Executive updates, decisions, escalations, launch readiness, risk, tradeoffs
- `director-review`: Artifact review, strategy review, operating model, metrics, coaching prompts
- `tools`: Google Workspace, Slack, Salesforce, and Jira specific prompt packs

## How to use

1. Start with `standard-context-block.md`.
2. Choose the prompt that matches your workflow.
3. Paste only sanitized and approved context.
4. Ask AI to separate facts from assumptions.
5. Review the output before publishing.

## Recommended prompt wrapper

```text
Use only the context provided. Do not invent missing facts. Separate facts, assumptions, open questions, and recommendations. Identify missing information that would improve the output.
```
