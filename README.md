# ai-automations

AI-assisted prompts, workflows, and examples for TPM productivity and program management. Built from real use - things that save time on actual work, not proof-of-concept demos.

The tools here are not about replacing judgment. They are about removing mechanical work so there is more time for the work that actually requires it.

Each workflow follows the same pattern: a **context or persona file** that carries stable domain knowledge, and a **prompt file** that drives the session interaction. Keeping them separate means you can reuse the domain knowledge across different prompt formats, and swap the prompt without rewriting the expertise.

---

## What Is Here

### Workflows

| Workflow | What It Does |
|----------|-------------|
| [Status Report Generator](status-report-generator/) | Reads a folder of raw inputs - meeting notes, Slack exports, RAID log updates, ticket summaries - and produces a structured draft status report. Nine sections including overall status, decisions needed, risks and issues, and a NEEDS REVIEW section that flags what requires TPM judgment before sending. Integrates with the Slack Crawler in tpm-toolbox. |
| [Landscape Planner](landscape-planner/) | AI landscape architect consultation for Sonoma County conditions. Give it your budget, yard situation, and goals. Receive a visual layout, phased implementation guide, plant shopping list, and budget breakdown. Covers fire safety, drought tolerance, deer and gopher pressure, and local nursery recommendations. |
| [App Builder](app-builder/) | Two-prompt system for going from a rough app idea to a working web application. The intake prompt interviews a non-technical person and produces a structured developer brief. The builder prompt takes that brief through six phases - idea refinement, tech stack, architecture, MVP scope, UI/UX direction, and feature-by-feature build with complete copy-paste-ready code. |

---

## The TPM Workflows, and Where They Live

These four were listed here as "coming" for a while. Three of them had already shipped into this
repo and the list did not keep up, which is a good argument for indexing what exists rather than
advertising what might.

| Workflow | What It Does | Where |
|----------|--------------|-------|
| Meeting Notes Processor | Takes raw meeting notes and extracts decisions, action items, and open questions in structured format. Output slots into the meeting notes tracker in [tpm-toolbox](https://github.com/ChefPlex/tpm-toolbox). | [meeting-notes-to-actions.md](prompts/junior-tpm/meeting-notes-to-actions.md) · worked example: [input](examples/messy-meeting-notes-input.md) / [output](examples/processed-meeting-notes-output.md) |
| Pre-Meeting Brief Generator | Given an agenda and participant list, produces a one-page brief: the one outcome worth protecting, what each participant will push on, which decisions can actually close, and the objection you would least like to be asked. | [pre-meeting-brief.md](prompts/senior-tpm/pre-meeting-brief.md) |
| Escalation Draft | Takes a problem description and produces a structured escalation: what is blocked, the impact, what has been tried, the decision needed, and the deadline. Hard to write under pressure, easier from a starting point. | [escalation-draft.md](prompts/senior-tpm/escalation-draft.md) · worked example: [sanitized escalation](examples/sanitized-escalation-example.md) |
| Compliance Intake Triage | Turns a regulatory requirement, audit finding, or control request into engineering work with owners, evidence needs, milestones, and risk visibility. First cut only, not a substitute for GRC review. | [compliance-intake-workflow.md](workflows/compliance-intake-workflow.md) |

Nothing is queued beyond this right now. Additions happen when a prompt has been used on real work
often enough to be worth writing down, not on a roadmap.

---

## Design Principles

**Output you can use, not output you have to rewrite.** Prompts here are tuned for specific formats and real contexts. They produce things that slot into existing workflows, not generic text that needs heavy editing.

**Transparent about what AI is good at and what it is not.** AI is good at structure, first drafts, and pattern recognition. It is not good at knowing your specific situation, your org dynamics, or what the executive in the room actually cares about. These tools handle structural work. Judgment stays with you.

**Documented well enough to adapt.** Every workflow includes the prompt, expected input format, expected output format, and notes on where it tends to go wrong. If you need to adapt it to your context, you should be able to do that without reverse-engineering it.

**Lightweight.** No frameworks, no dependencies where avoidable. Prompts you can run in Claude.ai or via API. If something requires infrastructure, it is documented clearly and kept minimal.

---

## How This Fits With the Other Repos

- **tpm-templates** - The output formats the status report generator produces match the templates there
- **program-reporting-frameworks** - The status and steering committee frameworks explain what goes in each section and why
- **tpm-toolbox** - The Slack Crawler produces intelligence briefs that feed directly into the status report generator; the canvas synthesis tool handles the other direction

---

## Contributing

If you have a prompt, workflow, or pattern that saves real time on meaningful work and can be documented well enough to be useful to someone else, open a PR or file an issue. The bar: it has to work, it has to be documented, and it has to be general enough to apply outside one specific organization.

---

*Built from experience running platform security, infrastructure, and compliance programs at enterprise scale. Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*
