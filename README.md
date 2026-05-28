# ai-automations

AI-assisted prompts, workflows, and examples for TPM productivity and program management. Built from real use - things that save time on actual work, not proof-of-concept demos.

The tools here are not about replacing judgment. They are about removing mechanical work so there is more time for the work that actually requires it.

Each workflow follows the same pattern: a **persona or context file** that carries stable domain knowledge, and a **prompt file** that drives the session interaction. Keeping them separate means you can reuse the domain knowledge across different prompt formats, and swap the prompt without rewriting the expertise.

---

## What Is Here

### Workflows

| Workflow | What It Does |
|----------|-------------|
| [Landscape Planner](landscape-planner/) | AI landscape architect consultation for Sonoma County conditions. Give it your budget, yard situation, and goals. Receive a visual layout, phased implementation guide, plant shopping list, and budget breakdown. Covers fire safety, drought tolerance, deer and gopher pressure, and local nursery recommendations. |
| [App Builder](app-builder/) | Two-prompt system for going from a rough app idea to a working web application. The intake prompt interviews a non-technical person and produces a structured developer brief. The builder prompt takes that brief through six phases - idea refinement, tech stack, architecture, MVP scope, UI/UX direction, and feature-by-feature build with complete copy-paste-ready code. |

---

## What Is Coming

### TPM Workflows

| Workflow | What It Will Do |
|----------|----------------|
| Status Report Generator | Feed it a week of meeting notes, ticket updates, and RAID log changes. Get a structured status report draft in your existing format. The hard part of status reporting is pulling signal from noise - this handles the first pass. |
| Meeting Notes Processor | Takes raw meeting notes and extracts decisions, action items, and open questions in structured format. One prompt, organized output. |
| Pre-Meeting Brief Generator | Given an agenda and participant list, generates a one-page brief: what each stakeholder likely cares about, what decisions are needed, and where the blockers are likely to be. |
| Escalation Draft | Takes a problem description and generates a structured escalation: what is happening, what the impact is, what has been tried, and what decision is needed. Hard to write under pressure. Easier with a starting point. |
| Compliance Intake Triage | Given a new regulatory requirement or audit finding, generates an initial analysis: likely scope, evidence probably needed, remediation timeline estimate. First cut only - not a substitute for GRC review. |

### How-It-Works Examples

| Example | What It Shows |
|---------|--------------|
| Persona + Prompt Pattern | How to separate stable domain knowledge (the persona) from session interaction logic (the prompt). The landscape planner is the reference implementation. |

---

## Design Principles

**Output you can use, not output you have to rewrite.** Prompts here are tuned for specific formats and real contexts. They produce things that slot into existing workflows, not generic text that needs heavy editing.

**Transparent about what AI is good at and what it is not.** AI is good at structure, first drafts, and pattern recognition. It is not good at knowing your specific situation, your org dynamics, or what the executive in the room actually cares about. These tools handle structural work. Judgment stays with you.

**Documented well enough to adapt.** Every workflow includes the prompt, expected input format, expected output format, and notes on where it tends to go wrong. If you need to adapt it to your context, you should be able to do that without reverse-engineering it.

**Lightweight.** No frameworks, no dependencies where avoidable. Prompts you can run in Claude.ai or via API. If something requires infrastructure, it is documented clearly and kept minimal.

---

## How This Fits With the Other Repos

- **tpm-templates** - The output formats these tools produce match the templates there
- **program-reporting-frameworks** - The status and steering committee tools feed into those frameworks
- **tpm-toolbox** - The Slack Canvas Status Synthesis and Slack Crawler tools in tpm-toolbox are the automation layer; prompts here are the reasoning layer

---

## Contributing

If you have a prompt, workflow, or pattern that saves real time on meaningful work and can be documented well enough to be useful to someone else, open a PR or file an issue. The bar: it has to work, it has to be documented, and it has to be general enough to apply outside one specific organization.

---

*Built from experience running platform security, infrastructure, and compliance programs at enterprise scale. Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*
