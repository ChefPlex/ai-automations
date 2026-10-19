# ai-automations

AI-assisted prompts, workflows, and examples for TPM productivity and program management. Built from real use: things that save time on actual work.

The tools here remove mechanical work so there is more time for the work that requires judgment.

Where a workflow needs stable domain knowledge, it keeps it in a **context or persona file** and lets a **prompt file** drive the session interaction. Keeping them separate means you can reuse the domain knowledge across different prompt formats, and swap the prompt without rewriting the expertise.

---

## Start Here

### If you're new to using AI in program work

Three documents, in this order, before any prompt:

1. **[Safety and Data Handling](safety-and-data-handling.md)** - what may go into a model and what may not. Read this first, because it decides which prompts you can use on real work.
2. **[Operating Principles](operating-principles.md)** - how the prompts here are meant to be used: AI drafts, a person decides.
3. **[Prompt Quality Rubric](prompt-quality-rubric.md)** - how to tell a prompt that will hold up from one that only demos well.

Then look at one input next to its output in [examples](examples/), for instance [messy meeting notes](examples/messy-meeting-notes-input.md) and what [came out of them](examples/processed-meeting-notes-output.md). Seeing the pair is faster than any amount of instruction.

### Or start from the problem in front of you

| Situation | Start Here |
|:---|:---|
| Someone handed you "we want AI over our own documents" | [Enterprise RAG Program](ai-programs/enterprise-rag-program/) |
| AI agents are getting tool access and nobody can list what they can touch | [Agentic AI Program](ai-programs/agentic-ai-program/) |
| A weekly status report is due and the inputs are a mess | [Weekly Status Workflow](workflows/weekly-status-workflow.md), or the [Status Report Generator](status-report-generator/) for a folder of raw notes |
| Meeting notes need to become owned action items | [Meeting Notes to Action Items](prompts/junior-tpm/meeting-notes-to-actions.md) |
| An executive needs an update or a decision from you | [Executive Program Update](prompts/senior-tpm/executive-program-update.md) and [Decision Memo](prompts/senior-tpm/decision-memo.md) |
| Something needs to be escalated without burning a relationship | [Escalation Draft](prompts/senior-tpm/escalation-draft.md) |
| A launch is close and nobody is sure it is ready | [Launch Readiness Workflow](workflows/launch-readiness-workflow.md) |
| You want a hard second opinion on your own program | [What Am I Missing](prompts/director-review/what-am-i-missing.md) and [Director-Level Program Review](prompts/director-review/director-level-program-review.md) |
| You are deciding where AI belongs in a team or company at all | [The Five Execution Tiers](frameworks/ai-execution-tiers.md), then the [Activity Mapping Method](frameworks/activity-mapping-method.md) |
| You are choosing an AI tool for regulated data | [AI Tool Decision Matrix](frameworks/ai-tool-decision-matrix.md) |
| People outside engineering want to build with AI and you cannot just say no | [AI Prototyping Sandbox Workflow](workflows/ai-prototyping-sandbox-workflow.md) |
| You need to know what is wrong with a codebase, ranked, before an audit does | [Four-Lens Codebase Audit Workflow](workflows/four-lens-codebase-audit-workflow.md) |

Everything else is browsable by kind: [prompts](prompts/) (by level: junior, senior, director), [workflows](workflows/), [frameworks](frameworks/), [AI programs](ai-programs/), [templates](templates/) and [examples](examples/). For reading paths across all the ChefPlex repos, see [I need to…](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md).

---

## What Is Here

### Workflows

| Workflow | What It Does |
|----------|-------------|
| [Status Report Generator](status-report-generator/) | Reads a folder of raw inputs - meeting notes, Slack exports, RAID log updates, ticket summaries - and produces a structured draft status report. Nine sections including overall status, decisions needed, risks and issues, and a NEEDS REVIEW section that flags what requires TPM judgment before sending. Integrates with the Slack Crawler in tpm-toolbox. |
| [App Builder](app-builder/) | Two-prompt system for going from a rough app idea to a working web application. The intake prompt interviews a non-technical person and produces a structured developer brief. The builder prompt takes that brief through seven phases - idea refinement, tech stack, architecture, MVP scope, UI/UX direction, feature-by-feature build with executed tests, and a human gate before going live. |

---

## Frameworks

The prompts and workflows above answer "how do I do this piece of work well." The [frameworks](frameworks/)
answer the question underneath that one: which work should AI be touching at all, who does it, and
where does the human stay.

| Framework | Answers |
|----------|--------------|
| [AI Execution Tiers](frameworks/ai-execution-tiers.md) | How much AI belongs in a given activity: a five-tier maturity model from human-only to AI-only, and how to classify without kidding yourself. |
| [Activity Mapping Method](frameworks/activity-mapping-method.md) | How to map an entire company's work against those tiers in about a week, at three levels of resolution. |
| [Multi-Agent Delivery Framework](frameworks/multi-agent-delivery-framework.md) | 19 roles across 8 phases, ideation through operations, with senior/junior tier selection logic and an audit trail. Describes the framework; the individual role specifications are not published. |
| [Multi-Agent Delivery: Orchestrator and Workflow](frameworks/multi-agent-delivery/) | The orchestrator prompt and the 8-phase workflow behind that framework, with every handoff, gate and exit criterion, so you can see how a run actually proceeds. |
| [AI Tool Decision Matrix](frameworks/ai-tool-decision-matrix.md) | What to buy and in what order, and why the AI layer is phase 4 of 5 rather than the first purchase. |
| [AI Governance Program Template](frameworks/ai-governance-program-template.md) | How to stand up the program that governs all of it: charter, decision rights, intake, risk tiers crossed with execution tiers, controls, inventory, metrics and cadence. |

Regulated environments change the adoption order. That overlay lives in
[security-program-playbooks](https://github.com/ChefPlex/security-program-playbooks/blob/main/ai-tooling-regulated-data.md).

---

## AI Programs

Program kits for running an AI system as a program, with the general program documents they build on in [tpm-templates](https://github.com/ChefPlex/tpm-templates).

| Program | What It Is |
|:---|:---|
| [Enterprise RAG Program](ai-programs/enterprise-rag-program/) | Running Retrieval-Augmented Generation as a program rather than an AI experiment. An architecture primer for the people making decisions about it, and a playbook with phases, seven workstreams, governance and risk tiers, plus templates for the charter, use case catalog, data source inventory, evaluation plan, RAID starter, milestone exit criteria, and definition of done. With a [worked example](ai-programs/examples/sample-rag-inventory-row-and-failure-trace.md). The security workstream lives in [security-program-playbooks](https://github.com/ChefPlex/security-program-playbooks/tree/main/enterprise-rag-security). |
| [Agentic AI Program](ai-programs/agentic-ai-program/) | One-page control register for AI agents with tool access: an agent inventory with a named human owner per agent, a tool-permission map, who holds go / no-go on irreversible and outbound actions, and a guardrail coverage table that records what each guardrail cannot see. |

---

## The TPM Workflows, and Where They Live

These four were listed here as "coming" for a while. Three of them had already shipped into this
repo and the list didn't keep up, which is a good argument for indexing what exists rather than
advertising what might.

| Workflow | What It Does | Where |
|----------|--------------|-------|
| Meeting Notes Processor | Takes raw meeting notes and extracts decisions, action items, and open questions in structured format. Output slots into the [meeting notes tracker](https://github.com/ChefPlex/tpm-templates/blob/main/meeting-notes-action-tracker.md) in tpm-templates. | [meeting-notes-to-actions.md](prompts/junior-tpm/meeting-notes-to-actions.md), with a worked example: [input](examples/messy-meeting-notes-input.md) / [output](examples/processed-meeting-notes-output.md) |
| Pre-Meeting Brief Generator | Given an agenda and participant list, produces a one-page brief: the one outcome worth protecting, what each participant will push on, which decisions can actually close, and the objection you would least like to be asked. | [pre-meeting-brief.md](prompts/senior-tpm/pre-meeting-brief.md) |
| Escalation Draft | Takes a problem description and produces a structured escalation: what is blocked, the impact, what has been tried, the decision needed, and the deadline. Hard to write under pressure, easier from a starting point. | [escalation-draft.md](prompts/senior-tpm/escalation-draft.md), with a worked example: [sanitized escalation](examples/sanitized-escalation-example.md) |
| Compliance Intake Triage | Turns a regulatory requirement, audit finding, or control request into engineering work with owners, evidence needs, milestones, and risk visibility. First cut only, not a substitute for GRC review. | [compliance-intake-workflow.md](workflows/compliance-intake-workflow.md) |

Nothing is queued beyond this right now. Additions happen when a prompt has been used on real work
often enough to be worth writing down, not on a roadmap.

---

## Design Principles

**Output you can use, not output you have to rewrite.** Prompts here are tuned for specific formats and real contexts. They produce things that slot into existing workflows, not generic text that needs heavy editing.

**Transparent about what AI is good at and what it's not.** AI is good at structure, first drafts, and pattern recognition. It's not good at knowing your specific situation, your org dynamics, or what the executive in the room actually cares about. These tools handle structural work. Judgment stays with you.

**Documented well enough to adapt.** Every workflow includes the prompt, expected input format, expected output format, and notes on where it tends to go wrong. If you need to adapt it to your context, you should be able to do that without reverse-engineering it.

**Lightweight.** No libraries or dependencies where avoidable. Prompts you can run in Claude.ai or via API. If something requires infrastructure, it is documented clearly and kept minimal.

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

## License

Copyright (c) 2026 Eric White. Licensed under [CC BY 4.0](LICENSE): use it, adapt it, put it to
work in your own program. Credit is the only condition.

---

**Part of the ChefPlex TPM portfolio** | Status: Active | [I need to… find the right document across all the repositories](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md) | [All repositories](https://github.com/ChefPlex)
