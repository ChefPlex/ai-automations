# Prompts

This directory contains reusable TPM prompts organized by level and workflow.

The prompts are meant to help with the messy middle of TPM work: turning scattered context into a clear artifact that names status, risk, ownership, and the next decision.

## Categories

- `junior-tpm`: Execution hygiene, action items, status, Jira cleanup, Slack summaries
- `senior-tpm`: Executive updates, decisions, escalations, launch readiness, risk, tradeoffs
- `director-review`: Artifact review, strategy review, operating models, metrics, and coaching prompts
- `tools`: Google Workspace, Slack, Salesforce, and Jira specific prompt packs

## Which one to use

Several prompts and workflows overlap. They are kept separate because the audience and the input differ; pick by those.

**Status and updates:**

| You have | Your reader is | Use |
|:---|:---|:---|
| Raw inputs for one week | The team and your manager | [weekly-status-update](junior-tpm/weekly-status-update.md), or the [weekly status workflow](../workflows/weekly-status-workflow.md) for the full routine around it |
| A whole reporting period of notes, Slack exports, RAID and tickets | Anyone; you want a complete draft and the evidence for each color | [status report generator](../status-report-generator/) |
| Inputs from many systems | Leadership | [executive-program-update](senior-tpm/executive-program-update.md) |
| A quarter's delivery, risk and customer data | A business review | [qbr-summary](senior-tpm/qbr-summary.md) |
| Tickets before a standup | The team, in the room | [standup-prep](junior-tpm/standup-prep.md) |
| One long thread | Whoever missed it | [slack-thread-summary](junior-tpm/slack-thread-summary.md) |

**Director review:**

| The question | Use |
|:---|:---|
| Is this finished document ready for leadership? | [artifact-critique](director-review/artifact-critique.md) |
| Is this plan the right plan, before anyone executes it? | [program-strategy-review](director-review/program-strategy-review.md) |
| How healthy is this running program, across strategy, execution, risk, metrics and communication? | [director-level-program-review](director-review/director-level-program-review.md) |
| The plan looks fine. What did I not see? | [what-am-i-missing](director-review/what-am-i-missing.md) |

Every prompt opens with **Where this fails**, right after when to use it. Read that part first.

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
