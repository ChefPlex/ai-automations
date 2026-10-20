# Standing Up an AI Governance Program

## What this is for

**An AI governance program is a standing set of decisions, owners and records. It is not a policy
PDF.** If you cannot say who approved a given AI use, what risk tier it sits in, what controls it
carries and when someone last looked at it, you do not have a program yet, whatever the policy says.

This document is a template for building one. It gives you the charter, the roles and decision
rights, the intake form, a way to tier use cases by risk, the inventory fields, a control set per
risk tier, the metrics and the review cadence. A fictional worked example at the end shows it running.

It sits beside [The Five Execution Tiers](ai-execution-tiers.md) and does not replace it. The two
answer different questions, and the program needs both:

| Axis | Question it answers | Where it lives |
|:---|:---|:---|
| **Execution tier** (1 to 5) | How is the work divided between a human and the AI, and where does the human stand? | [AI Execution Tiers](ai-execution-tiers.md) |
| **Risk tier** (Low, Medium, High, Prohibited) | How bad is a failure, for people, for the business, and with a regulator? | This document |

A meeting-notes summarizer running at execution tier 5 and a hiring-screen drafter running at
execution tier 3 sit in very different risk tiers. The tier 5 tool has less human involvement and far
less at stake. **The controls you require come from both axes together, never from one alone.**

⚠️ **This is not legal advice and not an ISO/IEC 42001 certification.** It is a starting structure,
checked against sources as of October 2026. The map of standards and regulations is in the
[frameworks README](README.md#where-this-sits-relative-to-the-ai-governance-standards); this page is
for running the program. The stance is the tiers document's: **a human is always in the loop, and
every use case has a named owner.**

---

## Start small, or start full: pick your path

Most organizations do not need the full set on day one. Pick the row that fits and stop there until
you have a reason to go further.

| Your situation | Build this | Skip for now |
|:---|:---|:---|
| Small organization, internal productivity use, no regulated data | One-page charter, inventory, intake form, quarterly review | Board, independent review, impact assessments |
| Customer-facing AI, or confidential or personal data in scope | All of the above, plus the risk-tiering rubric, control set and a monthly working group | Full impact assessments for Low and Medium |
| Regulated data, EU users, US federal work, or any decision about a person's job, credit, health, housing, education or benefits | The full template | Nothing |

**The inventory is never optional.** Every regime below starts from knowing what AI you run, and you
cannot tier what you have not found.

---

## 1. Charter

Keep it to one page. If it needs more, you are writing policy, and policy belongs in a separate
document the charter points at. For a full program charter structure, use the
[program charter template](https://github.com/ChefPlex/tpm-templates/blob/main/program-charter-template.md);
the block below is the AI-specific core.

```text
AI GOVERNANCE PROGRAM CHARTER                                   Version: ___  Date: ___

Purpose:        Why this program exists, in one sentence.
Scope (in):     [ ] Employee tools (paid, free tier, extensions)  [ ] Embedded vendor AI
                [ ] Systems we build or fine-tune  [ ] Agents and connectors  [ ] Pilots
Scope (out):    What this program does not govern, and who does.
Authority:      Who can stop an AI use, today, without a meeting: ________________
Principles:     No more than three. Example: "Every AI use has a named owner."
Risk appetite:  What the organization will accept, and will not, at each risk tier.
Review date:    The charter is re-read and re-signed by: ________
Sponsor:        Name, title, signature, date.
```

**The line that matters most is Authority.** A program that cannot stop anything is an advisory
mailing list.

The risk appetite line is where the NIST AI Risk Management Framework (AI RMF) GOVERN 1.3 lands:
*"Processes, procedures, and practices are in place to determine the needed level of risk management
activities based on the organization's risk tolerance."* ([NIST AI 100-1, January 2023](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf),
as of October 2026). The risk tiers in section 4 are that process.

**Scope rules to decide up front:**

- **Embedded AI is in scope.** A vendor switching on an AI feature is a new AI use, even though
  nobody bought anything. The NIST Generative AI Profile asks organizations to decide which embedded
  generative AI they exempt from the inventory (GV-1.6-002,
  [NIST AI 600-1, July 2024](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)). Decide it in
  writing, with a list, not by omission.
- **Free tools and pilots are in scope.** Most incidents happen in the pilot nobody registered.
- **Retired systems stay in the inventory one more review cycle,** and an ID is never reused.
- **When unsure, include it.** The US federal inventory guidance says it plainly: *"When unsure
  whether to report a use case, agencies should err on the side of inclusion"*
  ([OMB, Guidance on 2025 Agency Artificial Intelligence Reporting](https://github.com/ombegov/2025-Federal-Agency-AI-Use-Case-Inventory/tree/main/Reporting%20Instructions),
  as of October 2026).

---

## 2. Roles and decision rights

### The roles

| Role | What they do | Rule that keeps it honest |
|:---|:---|:---|
| **Executive sponsor** | Owns AI risk at the top. Signs the charter. Accepts High risk or names who may. | NIST GOVERN 2.3: *"Executive leadership of the organization takes responsibility for decisions about risks associated with AI system development and deployment."* |
| **Program owner** | Runs the program day to day. Owns the inventory, the intake queue, the rubric and the metrics. | Can be an existing leader with a second hat (a risk, security or data lead). US federal agencies may do the same with their Chief AI Officer (CAIO). Must be senior enough to be heard. |
| **Governance board** | Cross-functional. Decides High items, exceptions and rubric changes. | Security, privacy, legal, data, procurement, HR and the business. One chair, one vice-chair (often the program owner). Can be an existing risk committee with a new agenda item. |
| **Use-case owner** | Accountable for one AI use. Fills in intake, runs the controls, answers for it. | A named role and the person currently in it, never a team. Update the name when the person changes. The owner is a human; an agent the use runs is not the owner and does not get the owner's access. |
| **Independent reviewer** | Checks a High use case before risk is accepted. | Was not involved in building or buying it. Internal audit, a second-line risk function, or a peer team. |
| **Risk acceptor** | Signs to accept the residual risk. | A named person with the authority to carry that risk. A signature from someone who cannot stop the work is not acceptance. |
| **Operators and reviewers** | The people at the tier 4 gate, or using the output. | Trained before they start, and named, not "the team". |

The most specific public blueprint for these roles is US Office of Management and Budget (OMB)
Memorandum [M-25-21](https://www.whitehouse.gov/wp-content/uploads/2025/02/M-25-21-Accelerating-Federal-Use-of-AI-through-Innovation-Governance-and-Public-Trust.pdf)
(3 April 2025, as of October 2026): a named CAIO, a cross-functional board, a documented high-impact
determination, independent review and signed risk acceptance. **Private organizations are not bound
by it.** Lift the roles and steps, not the deadlines.

### RACI (Responsible, Accountable, Consulted, Informed)

**Fill in and adjust to your organization, keeping one A per row.** If a row has two, nobody is accountable.

| Activity | Sponsor | Program owner | Board | Use-case owner | Independent reviewer | Security, privacy, legal | Operators |
|:---|:---|:---|:---|:---|:---|:---|:---|
| Intake submission | I | C | | A/R | | C | C |
| Risk tiering | | A/R | C (High) | C | | C | |
| Pre-deployment testing | | C | | A/R | | C | C |
| Impact assessment (High) | | C | I | A/R | | C | |
| Independent review (High) | | A | I | C | R | C | |
| Approve go-live, Low and Medium | | A/R | | C | | C | |
| Approve go-live, High | I | R | A | C | C | C | |
| Risk acceptance, High | A/R | C | C | C | | C | |
| Exception or waiver | A | R | C | C | | C | |
| Monitoring and drift | | I | | A/R | | | R |
| Incident response | I | C | I | A/R | | R | R |
| Stop or disengage | I | A/R | I | R | | R | R |
| Decommission | | C | I | A/R | | C | |
| Inventory upkeep and metrics | I | A/R | I | R | | C | |
| Operator training | | A | | R | | C | R |

Note the "Stop or disengage" row. NIST MANAGE 2.4 calls for mechanisms *"to supersede, disengage, or
deactivate AI systems that demonstrate performance or outcomes inconsistent with intended use."*
**Write down who can pull the plug on each High use case, and test that they can.**

---

## 3. Intake form

One page. If it takes longer than twenty minutes to fill in, people will route around it and your
inventory will be fiction. The execution tier fields are the four from
[What to record](ai-execution-tiers.md#what-to-record), reused as they are.

```text
AI USE CASE INTAKE                                       Intake ID: ______  Date: ______

1.  Use case name:
2.  Use-case owner (a role and the person in it, not a team):
3.  Problem it solves, and how we will know it worked:
4.  Tool, model and version, and how we reach it (vendor app, API, embedded feature,
    self-hosted):
5.  Build, buy, or embedded in software we already run?
6.  Data it touches (public / internal / confidential / personal / regulated), and
    is there a signed agreement covering that data with the vendor?
7.  Who is affected by its outputs (employees, customers, the public)?
8.  Is the output a principal basis for a decision about a person's job, credit,
    insurance, health, housing, education, benefits, legal status or safety?   Y / N
9.  Does it profile people (evaluate or predict personal traits or behavior)?  Y / N
10. Execution tier (1 to 5), using the five classifying questions:
        Tier: ___   Owner: ___   Tool: ___   Gate: ___
11. Is any effect irreversible or outbound (a send, a payment, a deletion,
    a post, a deploy)?   Y / N
12. Named human oversight: who reviews, who can stop it:
13. Third parties and sub-processors that see the data:
14. Does it generate content published to the public, or talk to people who may not
    know it is AI?   Y / N
15. Where do its logs, memory and outputs get stored, and for how long?
16. If it acts as an agent (reads systems, calls tools, writes anywhere): what identity
    does it run under, and what can that identity reach? It gets its own identity, never
    the owner's or the requester's login, and short-lived tokens scoped to this task.
    What enforces the scope in code, outside the model?

PROGRAM USE ONLY
Risk tier: ________   Determined by: ________   Date: ________
Required controls (from section 5): ____________________________
Approver: ________   Decision: Approve / Approve with conditions / Decline / Exception
Next review date: ________
```

Questions 8 and 9 do most of the risk work. Question 8 is the federal "principal basis" test (section
4). Question 9 is there because the EU AI Act treats profiling in Annex III areas as always high-risk.

### Unknown vs Actionable intake answers

| Field | Unknown | Actionable |
|:---|:---|:---|
| Owner | "Customer Service" | "Contact Center Operations Manager (currently: [name])" |
| Agent access | "Uses the requester's login" | "Runs as its own service identity with read-only access to the claims system, on a token that expires in 15 minutes and covers only the claim being handled; a policy check in the API layer rejects anything outside that scope" |
| Gate | "Agents review the drafts" | "The handling agent approves each draft before send; send is blocked until they click approve; approvals are logged with their ID" |
| Data | "Customer data" | "Policy number, claim notes, caller name; no payment card data; vendor agreement covers personal data, signed 2026-08-14" |
| Benefit | "Faster replies" | "Cut median written-reply time from 11 minutes to under 5, measured from the ticketing system" |

The unknown answers are not wrong. They are unreviewable. Nobody can check a team, a vague gate or a
benefit with no measure.

The agent access answer is the one that most often reaches production unexamined. An agent running
on a person's login can do everything that person can, and a prompt injection then has the same
reach. Give each agent its own identity, short-lived tokens scoped to the task in hand, and a
deterministic check outside the model that enforces the scope. The design detail, including how
authority passes between chained agents, is in
[Authority Between Agents](https://github.com/ChefPlex/security-program-playbooks/blob/main/enterprise-rag-security/prompt-injection-threat-model.md#authority-between-agents).

---

## 4. Risk tiering: the second axis

Four risk tiers. Not six. A rubric that needs a training course will not be applied consistently, and
an inconsistent rubric is worse than none because it looks like control.

| Risk tier | Definition | Typical examples |
|:---|:---|:---|
| **Prohibited** | Uses banned by law where you operate, plus your own red lines from the charter. | EU AI Act Article 5 practices in EU scope; anything your risk appetite rules out |
| **High** | The output is a principal basis for a decision about a person's employment, credit, insurance, health, housing, education, benefits, legal status or safety; or it profiles people; or it touches regulated data; or it acts irreversibly or outbound at scale. | Ranking job applicants; scoring claims; triaging patients; automated account closure |
| **Medium** | Customer-facing or public-facing content; internal decisions with real human review; confidential data. | Drafting customer replies; summarizing vendor contracts; internal forecasting |
| **Low** | Internal productivity, no sensitive data, reversible, no decision about a person. | Meeting notes; code completion on non-production code; formatting slides |

The High definition deliberately overlaps the two most specific public sources. In the EU, *"AI use
cases that can pose serious risks to health, safety or fundamental rights are classified as
high-risk"* ([European Commission](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai),
as of October 2026), with the areas listed in Annex III (employment, education, essential services
and benefits, critical infrastructure, biometrics and others). M-25-21 calls AI high-impact when its
output *"serves as a principal basis for decisions or actions with legal, material, binding, or
significant effect on"* people's rights, access to services, health and safety.

### Tie-breakers

1. **Profiling people forces High.** No derogation.
2. **When two people disagree, go up one tier** and record why. This is the tiers document's "no
   it-depends" rule applied to risk.
3. **A step down needs a written reason.** Under EU AI Act Article 6(3), an Annex III system is not
   high-risk where it *"does not pose a significant risk of harm to the health, safety or fundamental
   rights of natural persons, including by not materially influencing the outcome of decision
   making"* (a narrow procedural or preparatory task, for example), and Article 6(4) says the
   provider *"shall document its assessment"*. Federal agencies can set aside a presumed high-impact
   finding the same way, in writing. Copy the pattern: one paragraph, signed by the program owner.
4. **Re-tier on change.** A new model version, new data, new users or a new purpose is a new intake.

### The cross-walk: risk tier by execution tier

This is where the two axes meet. Read across from the risk tier to the execution tier the intake
recorded.

| Risk tier | Tier 1 | Tier 2 | Tier 3 | Tier 4 | Tier 5 |
|:---|:---|:---|:---|:---|:---|
| **Prohibited** | Not permitted | Not permitted | Not permitted | Not permitted | Not permitted |
| **High** | Allowed | Allowed, High controls | Allowed, High controls | Allowed only with a named, blocking gate and a measured catch rate | Not permitted without a written board exception |
| **Medium** | Allowed | Allowed | Allowed | Allowed, gate named and blocking | Allowed if the three tier 5 conditions are written down, plus monitoring |
| **Low** | Allowed | Allowed | Allowed | Allowed | Allowed if the three tier 5 conditions are written down |

Two rules from the tiers document carry straight across. **Anything irreversible or outbound cannot
be tier 5, at any risk tier**, and its tier 4 gate blocks until approved and records who approved.
And a tier 4 gate is only real if a reviewer catches seeded known-bad items; see
[Tier 4](ai-execution-tiers.md#tier-4---ai-drives--humans-review). **At High risk, a rubber-stamp gate
is the most likely way this program fails.**

---

## 5. Control set by risk tier

Each row is a control. The cell says what it means at that tier. Blank means not required.

| Control | Low | Medium | High | Anchors |
|:---|:---|:---|:---|:---|
| Inventory entry | Yes | Yes | Yes | NIST GOVERN 1.6 |
| Named use-case owner | Yes | Yes | Yes | NIST GOVERN 2.1 |
| Data classification check | Yes | Yes | Yes | [Regulated data playbook](https://github.com/ChefPlex/security-program-playbooks/blob/main/ai-tooling-regulated-data.md) |
| Vendor agreement covers the data | If any non-public data | Yes | Yes | NIST GOVERN 6.1 |
| Pre-deployment testing | Smoke test | Test against intended use | Documented test plan and results | NIST MEASURE; AI 600-1 pre-deployment testing |
| Impact assessment | | Short form | Full form (below) | M-25-21 4(b); EU AI Act Art. 27 where it applies |
| Independent review | | | Yes, before risk acceptance | M-25-21 4(b) |
| Signed risk acceptance | | Use-case owner's executive | Sponsor or named delegate | NIST MANAGE 1.3, 1.4 |
| Human oversight specified | Owner named | Gate named | Gate named, blocking, catch rate measured quarterly | NIST GOVERN 3.2; EU AI Act Art. 26 |
| Operator training | Basic AI use guidance | Role training | Role training, plus competence checked before access | EU AI Act Art. 4; M-25-21 4(b) |
| Disclosure to affected people | | If public-facing or conversational | Yes, and before use on workers | EU AI Act Art. 50, 26(7), 26(11) |
| Monitoring and drift | Owner spot-checks | Monthly metric | Defined metric, threshold and alert | NIST MANAGE 4.1 |
| Log retention | Platform default | Defined period | At least six months, longer if your rules say so | EU AI Act Art. 26(6) |
| Appeal, override and fail-safe | | Override path | Appeal path for affected people, plus a fail-safe that works without the AI | M-25-21 4(b); NIST MANAGE 4.1 |
| Incident response | Report to program owner | Logged and reviewed | Runbook, owner, and communication plan | NIST GOVERN 4.3, MANAGE 4.3 |
| Change management | Re-intake on purpose change | Re-intake on model, data or purpose change | Re-intake and re-test on any change | Section 4 rule 4 |
| Decommission plan | | Yes | Yes, tested | NIST GOVERN 1.7 |
| Review frequency | Annual | Semiannual | Quarterly | Recommendation, not from a source |

The EU log figure is from deployer duties for high-risk systems: logs kept for a period *"of at least six months"* (Article 26(6)). Use it
as a floor for your own High tier even outside the EU; it is a sensible number.

### The High impact assessment

The federal minimum practices give the most usable public checklist. A High impact assessment should
record, at minimum:

```text
HIGH-RISK IMPACT ASSESSMENT                                Use case ID: ______

Intended purpose and expected benefit, with the metric:
Data used, its quality, and whether it fits the purpose:
Who could be harmed, and how (privacy, fairness, safety, access to services):
Test results before deployment:
Reassessment schedule:
Cost to run, including human review time:
Independent reviewer (name, team, confirms no involvement in building or buying it):
    Findings:
Residual risk, stated plainly:
Risk acceptance:  Name ________  Title ________  Signature ________  Date ________
```

If you deploy high-risk systems in EU scope as a public body, a provider of public services, or for
credit scoring and life or health insurance pricing, the EU AI Act also requires a fundamental rights
impact assessment (FRIA) under Article 27. Its contents overlap this form, but check the article. As
amended by the Omnibus, a FRIA can cross-reference or reuse the relevant parts of a data protection
impact assessment (DPIA) done under the General Data Protection Regulation (GDPR), so do not write
the same analysis twice.

### Exceptions register

An exception is a decision to run without a required control. Record per exception: the use case,
**one** control waived (no blanket waivers), the reason specific to this system, the compensating
control, the approver (board for High, program owner for Medium) and an **expiry date**. An exception
with no expiry is a policy change and goes to the board as one. This follows the federal waiver
pattern: a written determination by the CAIO, tracked centrally, reported to OMB within 30 days.

---

## 6. Inventory fields

NIST GOVERN 1.6: *"Mechanisms are in place to inventory AI systems and are resourced according to
organizational risk priorities."* The fields below are drawn from the 2025 federal inventory fields
and the NIST Generative AI Profile (GV-1.6-003). Keep the set short enough that someone will maintain it.

| Group | Field | Notes |
|:---|:---|:---|
| Identity | Use case ID | Never reused, even after retirement |
| Identity | Name, use-case owner, business unit, contact | Owner is a role |
| Description | Purpose and expected benefit | From intake Q3 |
| Description | Stage | Pre-deployment, pilot, deployed, retired (the federal four) |
| Description | Build, buy, or embedded; vendor | Embedded AI gets its own row |
| Description | Model, version, access mode | NIST AI 600-1 asks for underlying foundation models, versions and access modes |
| Description | Data used and data class | Including personal or regulated data |
| Description | Outputs and who they affect | From intake Q7 |
| Governance | Execution tier, owner, tool, gate | The four fields from the tiers document |
| Governance | Risk tier, date, determined by | Plus the step-down justification, if any |
| Governance | Assessments done, with links | Testing, impact assessment, independent review |
| Governance | Risk acceptor and date | Name and title |
| Governance | Monitoring metric and threshold | |
| Governance | Last review, next review | Drives the cadence in section 8 |
| Governance | Open exceptions | Links to the register |
| Governance | Retirement date | Keep the row one more cycle |

**Build the inventory from evidence, not from a survey.** Pull the platform's own listings of
connected apps and extensions, procurement and expense records, single sign-on logs and vendor
release notes. Then ask people. Self-report finds the tools people are proud of. The playbook on
[AI tooling in regulated environments](https://github.com/ChefPlex/security-program-playbooks/blob/main/ai-tooling-regulated-data.md)
has the same rule for connectors and agent tools.

---

## 7. Metrics

These are recommendations, not figures from any standard. Pick five to start.

| Area | Metric | Why it matters |
|:---|:---|:---|
| Coverage | Use cases found by discovery that were already in the inventory | The honest measure of whether intake works |
| Coverage | Percent with a named owner; percent risk-tiered | A row with no owner is not governed |
| Throughput | Days from intake to decision, by risk tier | If Low takes three weeks, people stop asking |
| High controls | Percent of High use cases with assessment, independent review, signed acceptance and live monitoring | All four, not an average |
| Gate health | Seeded-item catch rate and ask rate at each tier 4 gate | From the tiers document; the only test that separates a reviewer from a rubber stamp |
| Incidents | Count, time to detect, time to contain, near misses | Near misses are the leading indicator |
| Exceptions | Open, and aged past expiry | Aged exceptions are unmanaged risk |
| Training | Operators trained before access | |
| Reviews | Overdue reviews by risk tier | The first thing to slip |

⚠️ **Watch for metrics that only count paperwork.** "Policies published" and "tools approved" go up
whether or not anything is safer. The tiers document says it about automation, and it applies here:
a green report proves the form was filled in, not that anyone read it or acted on it.

---

## 8. Review cadence

NIST GOVERN 1.5 asks you to plan *"ongoing monitoring and periodic review of the risk management
process and its outcomes"*, *"including determining the frequency of periodic review."* Here is a
default frequency.

| Cadence | Who | What |
|:---|:---|:---|
| Weekly or every two weeks | Program owner and one or two specialists | Intake triage. Tier new items, approve Low, route the rest |
| Monthly | Governance board or working group | High decisions, exceptions, incidents, rubric questions |
| Quarterly | Program owner, reported to sponsor | Inventory reconciliation against discovery, metrics, seeded-item tests at tier 4 gates, High reviews |
| Annually | Sponsor and board | Charter, risk appetite and rubric re-read and re-signed; regulatory horizon check |
| On an event | Use-case owner and program owner | Incident, model or vendor change, new data, new purpose, new regulation |

### First 30, 60 and 90 days

| By day | Done means |
|:---|:---|
| 30 | Sponsor named. Program owner named. Charter signed. Inventory version zero from discovery. Any unknown tool cut off from regulated data until it goes through intake. |
| 60 | Intake form and rubric live. Board seated (or an existing committee given the agenda). The highest-risk items found in discovery assessed first. |
| 90 | Control set applied by tier. Metrics baseline taken. First quarterly review held, with the sponsor. |

This mirrors the federal sequence (CAIO within 60 days, board within 90 days, minimum practices within
365 days of M-25-21) at a faster pace, because a private program has fewer people to coordinate.

---

## 9. How the template maps to the sources

Use this as an aid for a conversation with your auditor or counsel, not as a compliance claim.

| Template part | NIST AI RMF 1.0 | EU AI Act | OMB M-25-21 |
|:---|:---|:---|:---|
| Charter, risk appetite | GOVERN 1, including 1.3 | | Agency AI strategy and policies |
| Roles, RACI | GOVERN 2.1, 2.3, 3.2 | Art. 26 human oversight assignment | CAIO, governance board |
| Intake, risk tiering | GOVERN 1.3; MAP | Art. 6 and Annex III classification | High-impact determination |
| Control set | MEASURE; MANAGE 1 to 4 | Art. 26, 27, 50 | Section 4(b) minimum practices |
| Inventory | GOVERN 1.6; AI 600-1 GV-1.6-001 to 003 | Classification depends on knowing what you run | Annual use case inventory |
| Exceptions | MANAGE 1.3, 1.4 | Art. 6(4) documented assessment | Waivers |
| Training | GOVERN 2 | Art. 4 AI literacy | Section 4(b) training |
| Metrics, cadence | GOVERN 1.5; MEASURE; MANAGE 4.1 | Art. 26 monitoring | Ongoing monitoring |
| Decommission | GOVERN 1.7 | | Retired use cases in inventory |

**NIST AI RMF 1.0** ([AI 100-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf), January 2023)
is voluntary. Its functions are GOVERN, MAP, MEASURE and MANAGE, and *"GOVERN is a cross-cutting
function that is infused throughout AI risk management and enables the other functions of the
process."* This template is mostly GOVERN. Version 1.0 is current as of October 2026, and NIST says *"The AI
RMF 1.0 is being revised as part of the White House AI Action Plan"*
([nist.gov](https://www.nist.gov/itl/ai-risk-management-framework), as of October 2026). Expect the
GOVERN numbering cited here to shift when the revision lands. The
[Generative AI Profile, AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) (July
2024) lists twelve generative AI risks, among them confabulation, data privacy, information security
and value chain and component integration: a good checklist for the High impact assessment.

**ISO/IEC 42001:2023** ([iso.org](https://www.iso.org/standard/42001)) is the international
management system standard for AI. If you plan to certify, buy the standard and map this template to
it clause by clause; do not rely on a summary of its structure, including this one.

**EU AI Act** ([Regulation (EU) 2024/1689](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32024R1689),
original text, as of October 2026). Binding within EU scope. It is risk-based: unacceptable (banned),
high, limited or transparency, and minimal. Most readers of this template are **deployers**, meaning
they use AI systems built by someone else. Dates of applicability:

| Date | What applies | Source status |
|:---|:---|:---|
| 2 February 2025 | Chapters I and II: prohibitions and AI literacy (Art. 4) | Original Art. 113 |
| 2 August 2025 | General-purpose AI (GPAI) model obligations, governance, penalties | Original Art. 113 |
| 2 August 2026 | General application, including Art. 50 transparency | Original Art. 113 |
| 2 December 2026 | New Art. 5 prohibitions: AI that generates non-consensual intimate imagery of an identifiable person, or child sexual abuse material | Omnibus, amended Art. 113(a) |
| 2 December 2026 | Art. 50(2) machine-readable marking, for generative systems already on the market before 2 August 2026 | Omnibus, new Art. 111(4) |
| 2 December 2027 | High-risk obligations for Annex III systems (Art. 6(2)), Chapter III Sections 1 to 3, which include the deployer duties in Art. 26 and 27 | Omnibus, amended Art. 113(c)(i) |
| 2 August 2028 | High-risk obligations for Annex I systems (Art. 6(1), product safety legislation) | Omnibus, amended Art. 113(c)(ii) |

The Digital Omnibus on AI ([Regulation (EU) 2026/1744](https://eur-lex.europa.eu/eli/reg/2026/1744/oj/eng),
adopted 8 July 2026, published 24 July 2026, in force 27 July 2026) moved the high-risk dates later.
It also rewrote the AI literacy duty in Article 4. The original asked providers and deployers to ensure
*"to their best extent, a sufficient level of AI literacy"*. The amended text says they *"shall take
measures to support the development of AI literacy"*, and adds: *"This obligation does not require
providers or deployers to guarantee any specific level of AI literacy of any individual."* Training
stays in the control set either way. No consolidated text of the amended Act was found as of October
2026, so read both.

**The high-risk deployer duties are not live yet, but classification under Article 6 needs an
inventory first.** Build the inventory and rubric before December 2027, not during it. Original-text
penalties (Art. 99) reach EUR 35 million or 7% of worldwide annual turnover for prohibited practices,
and EUR 15 million or 3% for most other obligations, whichever is higher. For small and medium-sized
enterprises (SMEs) it is whichever is lower, and the Omnibus extends that to small mid-cap enterprises
(SMCs).

**OMB M-25-21** ([3 April 2025](https://www.whitehouse.gov/wp-content/uploads/2025/02/M-25-21-Accelerating-Federal-Use-of-AI-through-Innovation-Governance-and-Public-Trust.pdf),
as of October 2026) binds US federal agencies only. It *"rescinds and replaces"* M-24-10, so do not
cite M-24-10 as current. Its clock ran from issue: CAIO within 60 days, a board within 90 days for
CFO Act (Chief Financial Officers Act) agencies, minimum practices for high-impact AI within 365 days
(3 April 2026), and an inventory at least annually. No replacement was found as of October 2026, but
check. If you sell to federal agencies, expect their questions to follow this structure.

US state AI laws and sector rules are not covered here. Check the current text where you operate.

---

## Worked example: Birchwood Mutual

*Fictional company. All names, figures and events are invented for illustration.*

**Situation.** Birchwood Mutual is a 600-person regional insurer with a claims unit and a call
center. Three departments adopted AI tools on their own. A vendor added an AI summarizer to the claims
system in a routine update. The chief operating officer (COO) asks a simple question in a board
meeting, "what AI do we run?", and nobody can answer it.

**Weeks 1 and 2.** The COO becomes sponsor. The enterprise risk manager takes the program owner role
as a second hat. The one-page charter names the program owner and the chief information security
officer (CISO) as able to stop any AI use. Discovery runs from sign-on logs, expense reports,
extension listings and vendor release notes. The CEO guessed six uses. Discovery finds 31, two of
them only in expense reports and one only in a vendor's release notes.

**Weeks 3 to 8: four intakes, tiered.**

| Use case | Execution tier | Risk tier | Outcome |
|:---|:---|:---|:---|
| Meeting-notes summarizer for internal staff | 3 | Low | Approved in two days. |
| Call-center reply drafter | 4 | Medium | Gate failed its first seeded test. See below. |
| Claims-triage scoring model | 5 | High | Approved with conditions after full assessment. |
| Vendor-embedded claims summarizer | 5 as shipped | High | Restricted to non-personal fields until the vendor agreement is fixed. |

**The reply drafter.** The program owner seeds 20 known-bad drafts into a week of normal traffic:
wrong policy numbers, a promise the company cannot keep, a reply to the wrong customer. Agents catch
4 of 20. That is not a gate; it is a log. The tier 4 label is withdrawn, and the drafter is limited to
internal use while three changes go in: rejecting a draft is a single click that opens a blank reply,
the queue routes only drafts that mention money or coverage through the gate, and each approval
records the agent. The retest catches 18 of 20. The tier 4 label goes back on.

**The claims-triage model.** It ranks incoming claims for adjuster attention. The intake answers yes to
question 8: it affects how fast a claimant gets a decision on an insurance benefit. The use-case owner
argues for a step down because the model "only does a preparatory task" and a human adjuster makes
every decision. The board rejects the step down in writing. Its reasoning: the ranking decides the
order and speed of decisions, so it materially influences the outcome, which is the test in the
Article 6(3) pattern. The model goes High.

The High controls, as run:

- **Impact assessment:** claims with short notes, often from older policyholders, may rank lower.
- **Independent review** by internal audit: the test set under-represents short claims. Vendor retests.
- **Risk acceptance** signed by the vice president (VP) of claims, who owns the budget and can stop it.
- **Monitoring:** median time to first adjuster touch, split by note length, alert at a 20% gap.
- **Fail-safe:** adjusters can switch to the unscored queue in date order at any time.
- **Appeal:** a claimant who disputes a delay can ask for manual review; the letter says how.

**A board minute that says no.**

```text
Item 4: Request to let the claims-triage model auto-close claims under the deductible
        (proposed execution tier 5).
Decision: Declined.
Reason:   Closing a claim is irreversible and outbound to the claimant. Not eligible for
          tier 5 at any risk tier. Resubmit as tier 4 with a blocking adjuster approval.
Owner:    VP Claims.  Revisit: next month's board.
```

**Quarter 1 metrics.**

| Metric | Result |
|:---|:---|
| Use cases inventoried, with a named owner | 31 of 31 |
| High use cases with all four High controls | 1 of 1 |
| Reply drafter seeded catch rate | 4 of 20, then 18 of 20 after redesign |
| Median days, intake to decision | Low 2, Medium 9, High 24 |
| Incidents | 1: the embedded summarizer sent claim text to a sub-processor not named in the agreement. Found at intake, contained by restricting fields. Vendor agreement amended. |
| Open exceptions | 0 |

**What went wrong.** The first rubric had six risk tiers. In the first month, two reviewers gave the
same use case three different tiers between them. The program owner cut it to four, and tier
disagreements dropped to near zero. The lesson is in section 4: if people cannot apply the rubric, it
is not a control.

---

## Where this breaks

- **The inventory is built from self-report.** You get the tools people want you to know about.
- **The board never says no.** If a quarter passes with no declines and no conditions, check whether
  anything real reaches it. A board that approves everything is a notification step.
- **The rubric is too fine.** Six tiers and weighted scores feel rigorous. Nobody applies them the
  same way twice.
- **Intake is too heavy.** If a Low tool takes three weeks, people stop registering tools. Coverage
  measured against discovery shows it; coverage measured against intake hides it.
- **Embedded AI is missed.** Nobody bought it, so nobody filed it.
- **Approvals never expire.** A use case approved two model versions ago is not the same use case.
- **The risk acceptor has no authority.** A signature from someone who cannot stop the work is decoration.
- **The tier 4 gate rots.** Every control in section 5 can be in place while the reviewer has stopped
  reading. Only the seeded-item test shows it.
- **The template is mistaken for compliance.** Where a regulation applies, it decides what you must
  show, and counsel decides what it means.

---

## Related

- [The Five Execution Tiers](https://github.com/ChefPlex/ai-automations/blob/main/frameworks/ai-execution-tiers.md): the first axis; how work is divided between people and AI
- [Activity Mapping Method](https://github.com/ChefPlex/ai-automations/blob/main/frameworks/activity-mapping-method.md): mapping a company's work to execution tiers in about a week
- [AI Tool Decision Matrix](https://github.com/ChefPlex/ai-automations/blob/main/frameworks/ai-tool-decision-matrix.md): what to buy and in what order
- [Frameworks README](https://github.com/ChefPlex/ai-automations/blob/main/frameworks/README.md): where this sits relative to the AI governance standards
- [AI Tooling in Regulated Environments](https://github.com/ChefPlex/security-program-playbooks/blob/main/ai-tooling-regulated-data.md): agreements before data, connector review, inventory from the platform's own listing
- [Healthcare AI Governance: From Policy to Proof](https://github.com/ChefPlex/learning-notes/blob/main/articles/healthcare-ai-governance-from-policy-to-proof.md): human oversight as an auditable record
- [Program Charter Template](https://github.com/ChefPlex/tpm-templates/blob/main/program-charter-template.md): the full charter structure
- [RACI Template (Waterfall)](https://github.com/ChefPlex/tpm-templates/blob/main/raci-template-waterfall.md): RACI conventions
- [The RAID Log Guide](https://github.com/ChefPlex/tpm-templates/blob/main/raid-log-guide.md): risk strategy (avoid, mitigate, transfer, accept) and review cadence

---

*Part of the [ChefPlex TPM portfolio](https://github.com/ChefPlex/tpm-templates/blob/main/PORTFOLIO-GUIDE.md). Maintained by [Eric White](https://www.linkedin.com/in/edwhite). Licensed under [CC BY 4.0](../LICENSE).*
