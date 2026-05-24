# ai-automations

AI-powered scripts, prompts, and workflows for TPM productivity and program management. Built from actual daily use: things that save real time on the job, not proof-of-concept demos.

The tools here are not about replacing judgment. They are about removing mechanical work so there is more time for the work that actually requires judgment: clarifying ambiguity, surfacing risk, aligning teams, making tradeoffs, and helping leaders make better decisions.

This repo is written from the perspective of a director-level Technical Program Manager leading platform security, infrastructure, compliance, customer trust, and engineering execution programs at enterprise scale.

---

## What Is Here Now

This repo now contains a practical TPM AI workflow library for teams working across Google Workspace, Slack, Salesforce, and Jira.

The first release includes prompts, workflows, examples, and safety guidance for:

- Weekly status reporting
- Executive program updates
- RAID log creation and summarization
- Jira hygiene reviews
- Slack thread summaries
- Meeting notes processing
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

The bar for inclusion is higher than simply having a prompt that works once. A prompt that works for one person in one context is not automatically a tool. A tool is documented, reproducible, safe to adapt, and general enough to help someone else do better TPM work.

---

## Why This Exists

TPMs spend too much time turning scattered inputs into usable program artifacts.

A single program update might require signal from:

- Jira epics, stories, blockers, and sprint notes
- Slack threads and stakeholder updates
- Google Docs, Sheets, and Slides
- Salesforce cases, account notes, opportunities, renewals, and escalations
- RAID logs
- Meeting notes
- Dashboards
- Executive conversations

The hard part is not always writing the artifact. The hard part is pulling the signal from the noise, identifying what changed, separating facts from assumptions, and making the next decision obvious.

This repo provides reusable prompts and workflows for that work.

---

## Start Here

Recommended first files:

1. [Safety and data handling](safety-and-data-handling.md)
2. [Operating principles](operating-principles.md)
3. [Standard context block](prompts/standard-context-block.md)
4. [Weekly status workflow](workflows/weekly-status-workflow.md)
5. [Executive program update prompt](prompts/senior-tpm/executive-program-update.md)
6. [Director artifact critique prompt](prompts/director-review/artifact-critique.md)
7. [Prompt quality rubric](prompt-quality-rubric.md)

---

## Quick Example

A TPM needs a weekly executive update.

Inputs:

- Jira epic summaries
- Slack blocker thread
- Google Doc meeting notes
- Salesforce customer escalation notes
- Current RAID log

Use:

- [Weekly status workflow](workflows/weekly-status-workflow.md)
- [Executive program update prompt](prompts/senior-tpm/executive-program-update.md)
- [Jira prompts](prompts/tools/jira.md)
- [Salesforce prompts](prompts/tools/salesforce.md)

Output:

- Executive summary
- Program health
- What changed this week
- Risks and blockers
- Decisions needed
- Next milestone

The TPM still owns the judgment. The prompt helps produce the first structured pass.

---

## Repo Structure

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

---

## How To Use The Prompts

Use the [standard context block](prompts/standard-context-block.md) first. Then paste the specific prompt below it.

A strong TPM prompt should include:

- Program objective
- Business or customer impact
- Audience
- Current phase
- Milestone or target date
- Jira context
- Slack context
- Google Doc, Sheet, Slide, or meeting note context
- Salesforce customer signal context, when relevant
- Known risks
- Known blockers
- Decision needed
- Desired output format

Do not use these prompts as a replacement for validation. Use them to accelerate structure, completeness, and clarity.

---

## Standard Workflow

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

---

## What Is Coming

The repo should stay practical and lightweight. Future additions should come from repeated use, not theoretical prompt ideas.

### Status Reporting

**Status Report Generator** - Feed it a week's worth of meeting notes, ticket updates, and RAID log changes. Get a structured status report in the format that matches the Communications Plan template in `tpm-templates`. The hard part of status reporting is not the writing. It is pulling the signal from a week of noise. This handles the first pass.

**RAID Log Summarizer** - Takes a populated RAID log and generates an executive-level risk summary: what is hot, what closed, and what needs a decision. Useful for steering committee prep.

### Meeting Support

**Meeting Notes Processor** - Takes raw meeting notes, including rough or stream-of-consciousness notes, and extracts decisions, action items, and open questions in the format from the meeting notes template in `tpm-templates`. One prompt, structured output.

**Pre-Meeting Brief Generator** - Given a meeting agenda and participant list, generates a one-page brief: what each participant likely cares about, what decisions are needed, and where the blockers are likely to be. Useful before steering committees and executive reviews.

### Program Health

**Program Health Check** - Given a charter, RAID log, and status history, generates a structured assessment of where the program stands relative to where it should be at this phase of the lifecycle. It surfaces issues that are easy to miss when you are close to the work.

**Escalation Draft** - Takes a problem description and generates a structured escalation: what is happening, what the impact is, what has been tried, and what decision or action is needed from the escalation target. Hard to write under pressure. Easier with a starting point.

### Compliance and Security

**Compliance Intake Triage** - Given a new regulatory requirement or audit finding, generates an initial analysis: which systems and programs are likely in scope, what evidence may be needed, and what the remediation timeline might look like. First cut only, not a substitute for GRC review.

**Evidence Request Translator** - Takes an auditor's evidence request, often written in auditor language, and translates it into plain language: what they are actually asking for, what a complete response looks like, and who in the organization likely owns it.

### Lightweight Scripts

Prompts come first because they require no setup and are easier to adapt. Scripts may be added later when they save enough time to justify the extra maintenance.

Potential script areas:

- Jira export summarization
- Markdown status report generation
- RAID log normalization
- Prompt pack indexing
- Local template generation

---

## Design Principles

**Output you can use, not output you have to rewrite.** The prompts here are tuned for TPM formats and enterprise operating rhythms. They should produce artifacts that slot into existing workflows.

**Transparent about what AI is good at and what it is not.** AI is good at structure, first drafts, summarization, and pattern recognition. It is not good at knowing your specific situation, your org dynamics, or what the executive in the room actually cares about. These tools handle the structural work. The judgment stays with you.

**Documented well enough to be adapted.** Every tool should include the prompt, expected input format, expected output format, review checklist, and notes on where it tends to go wrong. If you need to adapt it to your context, you should be able to do that without reverse-engineering it.

**Lightweight by default.** No heavy frameworks, no unnecessary dependencies, no complex setup. A prompt you can run in ChatGPT, Claude, Gemini, or an approved internal model is often more useful than a brittle automation that no one maintains.

**Built for real TPM work.** These are not generic productivity prompts. They are designed around program execution, stakeholder alignment, risk management, customer trust, compliance, infrastructure, and executive communication.

**Safe before clever.** Do not paste sensitive, confidential, restricted, regulated, or customer-identifying data into unapproved AI tools. Sanitize first. Validate everything before use.

---

## Tooling Context

These prompts are designed for TPMs working in a common enterprise environment:

### Google Workspace

Use for charters, meeting notes, executive docs, trackers, decision memos, and review decks.

Relevant prompts:

- [Google Workspace prompts](prompts/tools/google-workspace.md)
- [Executive program update](prompts/senior-tpm/executive-program-update.md)
- [Decision memo](prompts/senior-tpm/decision-memo.md)

### Slack

Use for thread summaries, blocker removal, stakeholder alignment, escalation drafting, and follow-up notes.

Relevant prompts:

- [Slack prompts](prompts/tools/slack.md)
- [Slack thread summary](prompts/junior-tpm/slack-thread-summary.md)
- [Escalation draft](prompts/senior-tpm/escalation-draft.md)

### Salesforce

Use for customer signal summaries, escalation briefs, customer impact analysis, and connecting platform work to business risk.

Relevant prompts:

- [Salesforce prompts](prompts/tools/salesforce.md)
- [Customer escalation workflow](workflows/customer-escalation-workflow.md)
- [Salesforce signal intake template](templates/salesforce-signal-intake-template.md)

### Jira

Use for epic reviews, sprint risk, acceptance criteria, dependency mapping, roadmap summaries, and translating ticket activity into outcomes.

Relevant prompts:

- [Jira prompts](prompts/tools/jira.md)
- [Jira hygiene review](prompts/junior-tpm/jira-hygiene-review.md)
- [Jira export field list](templates/jira-export-field-list.md)

---

## How This Fits With The Other ChefPlex Repos

These tools are designed to work alongside the content in the other ChefPlex repos:

- **tpm-templates** - output formats from this repo should map to reusable TPM templates
- **program-reporting-frameworks** - status, steering committee, QBR, and executive review workflows should feed directly into those frameworks
- **tpm-toolbox** - scripts here may eventually include toolbox-compatible automation
- **security-program-playbooks** - security, compliance, and customer trust workflows can support program playbooks
- **learning-notes** - system design and security concepts can provide technical context for TPM prompts

The repos are separate because templates, tools, notes, playbooks, and automation serve different purposes. They are designed to work together.

---

## What Not To Paste Into AI Tools

Do not paste these into unapproved AI systems:

- Customer names or identifying details
- Customer contracts, commercial terms, or renewal details
- API keys, passwords, certificates, secrets, tokens, or credentials
- Production logs with identifiers
- Source code or proprietary architecture details without approval
- Vulnerability details that are not cleared for the tool being used
- Personal data, regulated data, health data, payment data, or employee data
- Legal advice requests or privileged legal content
- Incident details that require restricted handling
- Unreleased product, roadmap, pricing, or go-to-market information without approval

See [safety-and-data-handling.md](safety-and-data-handling.md) for detailed guidance.

---

## Prompt File Format

Each prompt file should follow this structure:

```text
Purpose
Best used for
Inputs
Prompt
Expected output
Human review checklist
Data handling notes
Common failure modes
```

---

## Contribution Guidelines

If you have a prompt, script, or workflow that saves real time on TPM work and can be documented well enough to be useful to someone else, open a PR or file an issue.

A good contribution should:

- Solve a real TPM workflow problem
- Be reusable across programs
- Produce an actionable artifact
- Include data handling notes
- Make ownership, dates, risks, and decisions clear
- Avoid proprietary examples
- Use sanitized examples only
- Be general enough to apply outside one specific organization

The bar is simple: it has to work, it has to be documented, and it has to be useful beyond one person's context.

---

## Disclaimer

This repo is a practical enablement resource. It is not legal, compliance, security, privacy, HR, customer communication, or incident response advice. Always follow your company's approved AI, data handling, security, privacy, legal, and customer communication policies.

---

Built from experience running platform security, infrastructure, and compliance programs at enterprise scale. Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)
