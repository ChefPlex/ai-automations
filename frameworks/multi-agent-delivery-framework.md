# The Multi-Agent Delivery Framework

**19 roles, 8 phases, ideation through operations - with tier-selection logic and an audit trail.**

The execution tiers say *how much* AI belongs in an activity. This says *who does the work* when
that activity is building software, and it is the part most multi-agent write-ups skip: a list of
agents is not a delivery framework. A delivery framework has phases, gates, handoffs, and a record
of what was decided and by whom.

> **A note on what is published here.** This document describes the framework - the roles, the
> phases, the gates, and the selection logic. The individual role specifications are not published.
> The intent is that you can build your own version of this, or evaluate whether the approach is
> sound, without needing mine.

---

## The 19 roles

Roles are numbered, and the numbers are load-bearing: workflow maps reference roles by number, so
`(06)` in a process diagram is an unambiguous pointer rather than a job title that three people
would define differently.

| # | Role | Phase |
|---|---|---|
| 01 | Business Stakeholder | Ideation |
| 02 | Product Manager | Ideation / all |
| 03 | Business Analyst | Requirements |
| 04 | UX Researcher | Requirements |
| 05 | UX/UI Designer | Design |
| 06 | Software Architect | Architecture |
| 07 | Security Architect | Architecture |
| 08 | Backend Engineer | Engineering |
| 09 | Frontend Engineer | Engineering |
| 10 | Mobile Engineer | Engineering |
| 11 | DevOps Engineer | Engineering / Release |
| 12 | QA Lead | QA |
| 13 | QA Automation Engineer | QA |
| 14 | Manual Tester | QA |
| 15 | Release Manager | Release |
| 16 | Systems Administrator | Operations |
| 17 | Engineering Manager | Coordination |
| 18 | Scrum Master | Coordination |
| 19 | Project Manager | Coordination |

**Security is role 07, in the Architecture phase.** Not a review at the end, not a checklist bolted
onto release. If a threat model is going to change the architecture, it has to arrive while the
architecture is still soft.

---

## The 8 phases

| Phase | Key roles | Gate |
|---|---|---|
| 1 - Ideation & Strategy | Stakeholder, PM | PRD approval |
| 2 - Requirements *(parallel with 3)* | PM, BA, UX Researcher | Story approval |
| 3 - Architecture *(parallel with 2)* | Security Architect, Software Architect | Architecture approval |
| 4 - Design | UX/UI Designer | Wireframe approval |
| 5 - Engineering | Backend, Frontend, Mobile, DevOps | Phase exit criteria |
| 6 - QA | QA Lead, QA Automation, Manual Tester | QA sign-off |
| 7 - Release | Release Manager, DevOps, Sysadmin | Go / no-go |
| 8 - Operations | Sysadmin, Engineering Manager | Ongoing |

**Every phase ends in a named gate, and every gate is a human decision.** That is the through-line
with the execution tiers: agents do the work, a person decides whether it advances.

Phases 2 and 3 run in parallel deliberately. Requirements and architecture inform each other, and
serializing them produces either an architecture built for requirements that changed or
requirements written without knowing what is expensive.

---

## Tier selection: the decision that costs the most when you get it wrong

Each role can be run by a **senior** agent or a **junior** agent, and some work should not be an
agent at all. Choosing badly is the single most common failure, and it fails in two directions.

| Tier | Quality | Speed | Cost | Use for |
|---|---|---|---|---|
| **Senior** | High | Slower | Expensive | Reasoning, ambiguity, decisions |
| **Junior** | Adequate | Fast | Cheap | Execution against a complete spec - **with a mandatory senior review gate** |
| **Script** | Deterministic | Fastest | Negligible | Enumerating, scanning, validating more than ~10 items |

**Failure mode 1 - a senior agent doing execution.** Enumerating 200 files or generating report
stubs from a template burns expensive reasoning on work a script does better, because a script does
it the same way every time.

**Failure mode 2 - a junior agent doing reasoning.** This is the expensive one, because the output
*looks* finished. A junior agent asked to design a threat model produces a plausible document that
misses the non-obvious threat. The cost does not appear at generation time. It appears in rework,
or in an incident.

### 11 of 19 roles cannot be delegated

Eight roles have a junior variant. Eleven do not, and that asymmetry is the most useful thing the
framework knows about itself.

**Senior-only** - a mistake here propagates through every phase that follows:

| Role | Why |
|---|---|
| 01 Business Stakeholder | A human being. Not an agent task at all |
| 02 Product Manager | PRD mistakes cascade into every downstream artifact |
| 05 UX/UI Designer | Design quality is subjective; bad design means engineering rework |
| 06 Software Architect | Architectural decisions foreclose future options and are hard to reverse |
| 07 Security Architect | Missed threats surface at breach time - a 10x cost asymmetry |
| 17 Engineering Manager | Team health and escalation need full context |

**Junior available, with a mandatory senior review gate** - 03 Business Analyst, 11 DevOps,
13 QA Automation, 14 Manual Tester, 15 Release Manager, 16 Sysadmin, 18 Scrum Master,
19 Project Manager.

**Context-dependent** - 04, 08, 09, 12 can run junior for implementation once the design is settled,
senior for the design and the review pass.

🔑 **The review gate is what makes the cheap tier safe.** Junior output never flows downstream
without senior validation. Remove that gate and the framework is just a cheaper way to generate
work nobody checked - which maps exactly to how tier 4 fails in the execution-tier model, and it is
the same discipline in a different vocabulary.

---

## Audit trail

Multi-agent systems produce a lot of output and lose the reasoning behind it unless the reasoning is
written down as it happens. Four records, kept per project:

| Record | Holds |
|---|---|
| **Thread log** | Every handoff between roles - who passed what to whom, and when |
| **Cost log** | Per-agent token usage, so tier-selection mistakes show up as a number |
| **Decision log** | Every gate decision and the reasoning, including the ones that said no |
| **Narrative log** | What actually happened, in order |

⛔ **Artifacts are voided, never deleted.** A superseded artifact is renamed, not removed, and
handoff entries are never edited out. An audit trail with the embarrassing parts removed is not an
audit trail - and the superseded version is usually the one that explains why the current one looks
the way it does.

---

## Two gates that fire on every run

Both exist because the expensive failures in software delivery are decided early and discovered late.

**The Pre-Implementation Challenge (phase 3).** Before implementation starts, the architect
interrogates the scope: is the problem statement actually validated, where does this fail at scale,
is there a simpler alternative nobody priced. Logged to the decision record before work proceeds.

**The Engineering Manager Challenge Gate (phase 5).** A second, differently-motivated challenge at
the point where cost starts accruing fast.

Neither gate is advisory. Both are logged, and both can stop the run.

---

## Verification over assertion

The rule that came out of building real things with this, and the one worth stealing even if you
take nothing else:

> **"Code is written" is not "software works."**

Before an agent may declare a build complete it has to demonstrate it - serve the application over
HTTP rather than opening a local file, confirm no broken links, resolve every asset path, pass the
security lint gate. **An agent's report that it finished is evidence about the agent, not about the
software.**

---

## Scaling down

The full 19-role framework is correct for a substantial build and heavy for a small one. Two
reduced variants exist for that reason, and the fact that it tiers down cleanly is a property of
the design rather than an accident:

- **A review-only variant** - 5 reviewer roles (review lead, architect, security, backend, QA)
  against a diff or a codebase, with no build phase. Portable, and useful inside environments where
  a full framework cannot be installed.
- **A lightweight delivery variant** - 5 roles across 4 phases (requirements → design → build →
  test), one human approval gate, for a single feature rather than a program.

**Match the framework to the blast radius.** Running 19 roles at a one-page change is the same
mistake as a senior agent enumerating files, one level up.
