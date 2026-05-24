# Repo Manifest

This manifest summarizes the package. It is here so a TPM can scan the repo quickly and know where to start.

## Root files

| File | Purpose |
|---|---|
| `README.md` | Repo overview, usage model, and starting points |
| `operating-principles.md` | Practical principles for AI-assisted TPM work |
| `safety-and-data-handling.md` | Data handling guidance for Google Workspace, Slack, Salesforce, and Jira |
| `prompt-quality-rubric.md` | Rubric for deciding whether a prompt is ready to reuse |
| `REPO_MANIFEST.md` | This file index |

## Prompt categories

| Directory | Purpose |
|---|---|
| `prompts/junior-tpm` | Execution hygiene, status, action items, Jira cleanup, Slack summaries |
| `prompts/senior-tpm` | Executive updates, decisions, escalations, launch readiness, risk, tradeoffs |
| `prompts/director-review` | Program reviews, strategy checks, operating models, metrics, and coaching prompts |
| `prompts/tools` | Google Workspace, Slack, Salesforce, and Jira prompt packs |

## Workflows

| Workflow | Use when |
|---|---|
| `weekly-status-workflow.md` | Weekly status needs to pull from Jira, Slack, docs, and customer signals |
| `customer-escalation-workflow.md` | Customer signals show delivery risk, urgency, or leadership attention |
| `launch-readiness-workflow.md` | A program is close to launch and needs a go or no go view |
| `compliance-intake-workflow.md` | Audit, policy, or control requests need to become engineering work |
| `executive-review-workflow.md` | Leadership needs a clean view of outcomes, risks, and decisions |

## Templates

| Template | Purpose |
|---|---|
| `weekly-status-input-template.md` | Collect weekly program inputs before prompting |
| `salesforce-signal-intake-template.md` | Summarize customer signals safely |
| `jira-export-field-list.md` | Export only the Jira fields that are useful for TPM workflows |

## Examples

The examples are sanitized and fictional. They show the shape of a good artifact without carrying real company, customer, security, or commercial data.

## Suggested first pass

1. Read the safety guide.
2. Read the operating principles.
3. Try the weekly status workflow with sanitized data.
4. Compare the output to the examples.
5. Use the rubric before adding new prompts.

PS: The repo is only useful if the files stay practical. If something reads nicely but does not help a TPM make a decision, it needs more work.
