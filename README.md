# ai-automations

AI-powered scripts, prompts, and workflows for TPM productivity and program management. Built from actual daily use: things that save real time on the job, not proof-of-concept demos.

The point is not to replace judgment. The point is to remove some of the mechanical work so TPMs have more room for the work that actually requires judgment: clarifying ambiguity, surfacing risk, aligning teams, making tradeoffs, and helping leaders make better decisions.

This repo is written from the perspective of a director-level Technical Program Manager leading platform security, infrastructure, compliance, customer trust, and engineering execution programs at enterprise scale.

## What is here now

This repo contains a practical TPM AI workflow library for teams working across Google Workspace, Slack, Salesforce, and Jira.

The first release covers the work TPMs do every week:

- Weekly status reporting
- Executive program updates
- RAID log creation and cleanup
- Jira hygiene reviews
- Slack thread summaries
- Meeting notes to action items
- Decision memos
- Escalation drafts
- Dependency mapping
- Risk burndown planning
- Technical tradeoff analysis
- Launch readiness reviews
- QBR summaries
- Customer signal summaries from Salesforce context
- Director-level artifact reviews
- Program strategy reviews
- Operating model design
- Influence without authority planning
- Blameless retrospectives
- Compliance intake workflows

The bar for inclusion is higher than having a prompt that worked once. A prompt that only works for one person in one meeting is not really a tool yet. A tool is documented, reusable, safe to adapt, and clear enough that another TPM can use it without needing the backstory.

## Why this exists

TPMs spend a lot of time turning scattered inputs into usable program artifacts.

A single weekly update might pull signal from Jira epics, Slack threads, Google Docs, Sheets, Salesforce cases, meeting notes, dashboards, and a few hallway conversations that never quite made it into a system of record. The writing is not always the hard part. The hard part is figuring out what changed, what is real, what is assumed, what is blocked, and what decision needs to happen next.

This repo is meant to help with that middle step.

AI can get a first pass into shape quickly. The TPM still owns the judgment. That is where the job is.

## Start here

Read these first:

1. [Safety and data handling](safety-and-data-handling.md)
2. [Operating principles](operating-principles.md)
3. [Standard context block](prompts/standard-context-block.md)
4. [Weekly status workflow](workflows/weekly-status-workflow.md)
5. [Executive program update prompt](prompts/senior-tpm/executive-program-update.md)
6. [Director artifact critique prompt](prompts/director-review/artifact-critique.md)
7. [Prompt quality rubric](prompt-quality-rubric.md)

Not a big deal if you start somewhere else, but the safety file should come first. Bad inputs create bad outputs, and sometimes they create data handling problems no one needed.

## Quick example

A TPM needs a weekly executive update.

The raw material is spread across:

- Jira epic summaries
- A Slack blocker thread
- Google Doc meeting notes
- Salesforce customer escalation notes
- The current RAID log

The TPM uses:

- [Weekly status workflow](workflows/weekly-status-workflow.md)
- [Executive program update prompt](prompts/senior-tpm/executive-program-update.md)
- [Jira prompts](prompts/tools/jira.md)
- [Salesforce prompts](prompts/tools/salesforce.md)

The output should make these things clear:

- Current program health
- What changed this week
- What risk increased or decreased
- What is blocked
- What decision is needed
- Who owns the next action

The prompt does not decide the status. It helps organize the evidence so the TPM can make the call cleanly.

## Repo structure

```text
ai-automations/
  README.md
  operating-principles.md
  safety-and-data-handling.md
  prompt-quality-rubric.md
  REPO_MANIFEST.md

  prompts/
    README.md
    standard-context-block.md

    junior-tpm/
      README.md
      weekly-status-update.md
      meeting-notes-to-actions.md
      jira-hygiene-review.md
      slack-thread-summary.md
      raid-log-builder.md
      standup-prep.md
      acceptance-criteria-builder.md

    senior-tpm/
      README.md
      executive-program-update.md
      decision-memo.md
      escalation-draft.md
      dependency-map.md
      risk-burndown-plan.md
      technical-tradeoff-analysis.md
      launch-readiness-review.md
      qbr-summary.md

    director-review/
      README.md
      artifact-critique.md
      program-strategy-review.md
      what-am-i-missing.md
      director-level-program-review.md
      influence-without-authority-plan.md
      operating-model-design.md
      metrics-and-instrumentation-plan.md
      blameless-retrospective.md

    tools/
      README.md
      google-workspace.md
      slack.md
      salesforce.md
      jira.md

  workflows/
    README.md
    weekly-status-workflow.md
    customer-escalation-workflow.md
    launch-readiness-workflow.md
    compliance-intake-workflow.md
    executive-review-workflow.md

  templates/
    README.md
    weekly-status-input-template.md
    salesforce-signal-intake-template.md
    jira-export-field-list.md

  examples/
    README.md
    sanitized-weekly-status-example.md
    sanitized-escalation-example.md
    sanitized-decision-memo-example.md
    sanitized-launch-readiness-example.md
```

## How to use the prompts

Start with the [standard context block](prompts/standard-context-block.md). Then paste the specific prompt below it.

A useful TPM prompt usually needs:

- Program objective
- Customer or business impact
- Audience
- Current phase
- Milestone or target date
- Jira context
- Slack context
- Google Doc, Sheet, Slide, or meeting note context
- Salesforce customer signal context, when relevant and approved
- Known risks
- Known blockers
- Decision needed
- Desired output format

Do not use these prompts as a replacement for validation. Use them to get to a cleaner first draft, identify gaps, and make the next conversation sharper.

## Standard workflow

```text
1. Gather the relevant source material.
2. Remove or anonymize sensitive information.
3. Add the standard context block.
4. Run the relevant prompt.
5. Review the output for accuracy, tone, missing context, risk language, and ownership.
6. Convert the output into the final artifact.
7. Publish in the right system of record.
8. Update Jira, Slack, Salesforce, or Google Workspace links as needed.
```

A draft is not done until the system of record is updated. The prettiest status update in the world does not help much if Jira still says the blocked work is green.

## What good output looks like

Good output does not just sound polished. It helps the reader act.

A good TPM artifact should answer:

- What changed?
- Why does it matter?
- What is at risk?
- Who owns the next step?
- What decision is needed?
- What happens if we do nothing?

That last question matters. A lot of program risk hides in silence.

## Safety first

Do not paste sensitive data into unapproved tools.

That includes customer names, contract terms, renewal details, account notes, secrets, certificates, private keys, internal architecture details, vulnerability details, source code, production logs, legal content, restricted incident details, employee data, personal data, health data, payment data, and unreleased roadmap commitments.

When in doubt, reduce the input to the minimum useful shape:

```text
Customer A in the financial services segment has a renewal risk tied to delayed delivery of Capability X. The exact account name, revenue figure, and contract language have been removed.
```

That is usually enough for a useful program summary without carrying data you do not need.

## How this fits with the other repos

This repo sits next to the broader TPM materials:

- `tpm-templates` for reusable program artifacts
- `program-reporting-frameworks` for executive reporting patterns
- `security-program-playbooks` for security and infrastructure program execution
- `learning-notes` for technical TPM background and system design concepts

This repo is the AI layer. It helps turn messy inputs into better TPM artifacts faster.

## What this is not

This is not a collection of clever prompts for their own sake.

It is not a shortcut around understanding the program.

It is not a replacement for stakeholder conversations, engineering judgment, customer context, security review, legal review, or executive decision-making.

It is a working set of tools for getting from scattered information to a clearer next step.

## Contribution standard

A new prompt or workflow should be added only if it meets this standard:

- It solves a real TPM problem
- It explains when to use it
- It names the inputs needed
- It produces a useful artifact
- It includes human review checks
- It has data handling notes
- It helps someone make a decision or reduce risk

PS: If a prompt only makes something sound nicer, it probably does not belong here yet. Nice is fine. Useful is the bar.
