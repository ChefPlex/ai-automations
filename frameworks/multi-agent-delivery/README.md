# Multi-Agent Delivery Framework: Orchestrator and Workflow

The orchestrator prompt and the 8-phase workflow of a multi-agent software delivery framework: 19 roles, ideation through operations. It runs on Claude Code (Anthropic's agentic coding tool). The prompts are plain Markdown, so any agent runtime that can read a file and spawn a sub-agent could run them.

The role definitions are kept private. The orchestrator and the workflow are published so a reader can see how the framework actually runs, down to which gate stops the run for a person. The reasoning behind the design is in the [write-up](../multi-agent-delivery-framework.md).

The prompts call the framework by its working name, `prog-team`.

Its QA roles are in repeated use at a healthcare startup, auditing requirements-to-code traceability.

---

## What is in this folder

| File | What it holds |
|:---|:---|
| [`orchestrator.md`](orchestrator.md) | The orchestrator prompt. It reads the project idea, spawns each role in order, enforces the gates and writes the logs. |
| [`high-level-flow.md`](high-level-flow.md) | The 8-phase workflow, every handoff between roles, and the exit criteria for each phase. |

Not published: the 27 role definitions (19 senior roles and 8 junior variants), the tier and script-spawning guides, and the 13-document project template. Where the orchestrator says "your role definition", that is the text it would paste in from one of those files. The project file names it uses (`02-prd.md`, `09-decision-log.md`, `threads.md`, `costs.md`) are the documents a run creates and writes to.

---

## The 19 roles

The numbers are part of the design. The workflow refers to roles by number, so `(06)` always means the same role.

| # | Role | Phase | Junior variant |
|:---|:---|:---|:---|
| 01 | Business Stakeholder | Ideation | None. This is the human owner, never an agent. |
| 02 | Product Manager | Ideation, all | No |
| 03 | Business Analyst | Requirements | `03j` |
| 04 | UX (user experience) Researcher | Requirements | No |
| 05 | UX/UI Designer | Design | No |
| 06 | Software Architect | Architecture | No |
| 07 | Security Architect | Architecture | No |
| 08 | Backend Engineer | Engineering | No |
| 09 | Frontend Engineer | Engineering | No |
| 10 | Mobile Engineer | Engineering | No |
| 11 | DevOps Engineer | Engineering, Release | `11j` |
| 12 | QA Lead | QA | No |
| 13 | QA Automation Engineer | QA | `13j` |
| 14 | Manual Tester | QA | `14j` |
| 15 | Release Manager | Release | `15j` |
| 16 | Systems Administrator | Operations | `16j` |
| 17 | Engineering Manager | Coordination | No |
| 18 | Scrum Master | Coordination | `18j` |
| 19 | Project Manager | Coordination | `19j` |

Security is role 07 and runs before the architect, because a threat model written after the architecture is fixed only adds cost.

## The 8 phases

| Phase | Lead roles | Ends with |
|:---|:---|:---|
| 1 - Ideation and Strategy | 01, 02 | PRD (product requirements document) approval by the stakeholder |
| 2 - Requirements | 03, 04 | Functional specification (runs alongside phase 3) |
| 3 - Architecture and Security | 07, then 06 | Threat model, then architecture after a two-pass challenge |
| 4 - Design | 05 | Wireframe approval by the stakeholder |
| 5 - Engineering | 08, 09, 10, 11 | Engineering Manager challenge gate first, then exit criteria |
| 6 - QA | 12, 13, 14 | QA (quality assurance) sign-off with a list of what was not tested |
| 7 - Release | 15, 11, 16 | Go / no-go, made by the stakeholder |
| 8 - Operations | 16, 17 | No exit gate. Runs until the product is retired. |

Roles 17, 18 and 19 run across every phase as the coordination layer.

The Software Architect starts after the Security Architect and the Business Analyst finish. An earlier version ran all four in parallel, and the architect designed without the threat model and the specification it lists as inputs.

---

## Choosing a tier

Every task goes to one of three places.

| The task | Goes to | Why |
|:---|:---|:---|
| Needs judgment, resolves ambiguity, or makes a decision with downstream cost | Senior agent | A wrong call here propagates through every later phase. |
| Executes against a complete spec, runs a checklist, or fills a template | Junior agent, then a senior review | Cheaper and faster. The review gate is what makes it safe. |
| Enumerates, scans or validates more than about 10 items | A script | A script does the same thing every time and costs almost nothing. |

Both tiers run the same model. The saving comes from scope: a junior role has a narrower mandate (execute, do not decide), so it takes fewer turns and reads less. Junior output never moves downstream without a senior review. A junior agent given reasoning work produces something that looks finished, and the cost shows up later as rework.

---

## Rules that hold on every run

- **Only the orchestrator spawns.** A role agent does its work and returns. It does not start another agent.
- **A spawned role cannot ask the stakeholder anything.** Challenge steps therefore run as two spawns. Pass 1 returns questions. The orchestrator asks the stakeholder once. Pass 2 receives the answers word for word and produces the documents.
- **No requirement is cut without approval.** An internal gate may propose removing or deferring scope. The proposal takes effect only when the stakeholder approves it.
- **Two rollbacks per phase, then stop.** A third rollback is a design problem, and it goes to the stakeholder with both attempts.
- **Irreversible or outbound actions belong to the stakeholder.** That covers deploys, store submissions, sends and deletions.
- **Each role definition says when not to run it.** The format comes from *The Art of Agile Development* (James Shore and Shane Warden).

---

## Limits

- **Most of the controls are prose.** Roles are spawned as general-purpose agents that hold the spawn tool. The delegation limit, the rollback bound and the gates hold only if the orchestrator follows its instructions. Nothing here enforces them in code.
- **The tier split is design judgment.** No role has been removed and the run repeated to measure the effect. The cost log measures cost and time, not quality.
- **A senior review on the same model is not independent.** The same model with a similar prompt tends to make the same mistakes. A review that counts brings a different model, the source material or an executed test.
- **It is heavy for small work.** Nineteen roles suit a new product. A one-page change belongs in a single agent session or a lighter change workflow.
- **The sample projects are not included.** The framework was exercised on two small static-site builds. Their outputs named real businesses and carried local paths, so they are not published.
- **These files do not run on their own.** They show the sequence, the gates and the prompts. Running them means writing your own 19 role definitions first.

---

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../../LICENSE).*
