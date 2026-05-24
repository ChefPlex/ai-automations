# Repo Manifest

This manifest is the quick map for the repo. It is here so a TPM can scan the package, pick a useful starting point, and avoid treating a prompt library like a magic box.

## Root files

| File | Purpose |
|---|---|
| `README.md` | Repo overview, usage model, flagship workflows, and contribution standard |
| `operating-principles.md` | Practical principles for AI-assisted TPM work |
| `safety-and-data-handling.md` | Data handling guidance for Google Workspace, Slack, Salesforce, and Jira |
| `prompt-quality-rubric.md` | Rubric for deciding whether a prompt is ready to reuse |
| `REPO_MANIFEST.md` | This file index |

## Best starting points

| File | Start here when |
|---|---|
| `safety-and-data-handling.md` | You are using real work context and need to know what not to paste |
| `operating-principles.md` | You want the working rules for responsible AI-assisted TPM work |
| `prompts/standard-context-block.md` | You need the reusable context block that makes the prompts work better |
| `workflows/weekly-status-workflow.md` | You need to turn scattered inputs into a weekly status update |
| `prompts/senior-tpm/executive-program-update.md` | You need a leadership-ready program update from sanitized context |
| `prompts/director-review/artifact-critique.md` | You want a hard review before sending an artifact upstream |
| `prompt-quality-rubric.md` | You are deciding whether a prompt is good enough to keep |

## Prompt categories

| Directory | Purpose |
|---|---|
| `prompts/junior-tpm/` | Execution hygiene: status, action items, Jira cleanup, Slack summaries, RAID logs, standup prep, acceptance criteria |
| `prompts/senior-tpm/` | Program leadership: executive updates, decisions, escalations, dependencies, risk, tradeoffs, launch readiness, QBRs |
| `prompts/director-review/` | Review and coaching: artifact critique, strategy checks, operating models, metrics, retrospectives, influence plans |
| `prompts/tools/` | Tool-specific prompt packs for Google Workspace, Slack, Salesforce, and Jira |

## Workflows

| Workflow | Use when |
|---|---|
| `weekly-status-workflow.md` | Weekly status needs to pull from Jira, Slack, docs, and customer signals |
| `customer-escalation-workflow.md` | Customer signals show delivery risk, urgency, or leadership attention |
| `launch-readiness-workflow.md` | A program is close to launch and needs a go or no-go view |
| `compliance-intake-workflow.md` | Audit, policy, or control requests need to become engineering work |
| `executive-review-workflow.md` | Leadership needs a clean view of outcomes, risks, decisions, and asks |

## Templates

| Template | Purpose |
|---|---|
| `weekly-status-input-template.md` | Collect weekly program inputs before prompting |
| `salesforce-signal-intake-template.md` | Summarize customer signals safely before using them in a prompt |
| `jira-export-field-list.md` | Export only the Jira fields that are useful for TPM workflows |

## Examples

The examples are sanitized and fictional. They show the shape of a good artifact without carrying real company, customer, security, or commercial data.

| Example | Purpose |
|---|---|
| `sanitized-weekly-status-example.md` | Shows a weekly status output with health, risks, blockers, and decisions needed |
| `sanitized-escalation-example.md` | Shows how to frame an escalation without turning it into theater |
| `sanitized-decision-memo-example.md` | Shows how to separate options, tradeoffs, recommendation, and decision owner |
| `sanitized-launch-readiness-example.md` | Shows how to make launch readiness visible without hiding gaps |

## Suggested first pass

1. Read the safety guide.
2. Read the operating principles.
3. Try the weekly status workflow with sanitized data.
4. Compare the output to the examples.
5. Use the rubric before adding new prompts.
6. Add or improve a prompt only when it has review checks and a clear failure mode.

## Maturity rule

A file is ready for broad use only when it explains:

- What it does
- When to use it
- What inputs it expects
- What output it should produce
- Where it fails
- What a human must validate
- What data should not be pasted into the tool

If something reads nicely but does not help a TPM make a decision, it needs more work.
