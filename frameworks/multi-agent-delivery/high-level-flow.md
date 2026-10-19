# High-Level Program Flow

How work moves through the team, from the first idea to deployed, operating software. Each arrow is a primary handoff: the output of one role becomes the input of the next. This file is the reference for workflow sequence. When the orchestrator or a role asks what comes next, the answer is here.

---

## On exit criteria: read before adding or changing one

These are **convergence criteria, not effort caps.** Each one asks whether the artifact is in a given state, never how many rounds it took to get there. **Do not replace one with an iteration limit.** A cap stops a loop without knowing whether the work converged. A criterion stops it because the work is done, and can say so.

**Why this section exists.** The 19 role definitions declare **117 artifact flows**, and **18 of them are mutual**: two roles each need something from the other. Architect and Security Architect, Designer and UX Researcher, Backend and DevOps. **All 18 resolve inside a single phase.** That is normal iteration, and the phase structure allows it by design. The problem is that an iteration loop between two agents has no natural stopping point. A human pair converges on judgment; two agents will go back and forth until something tells them to stop. Before this section was written, **one phase of eight declared what "done" meant**: Phase 5, with six checkable lines. The other seven declared gates and sign-offs without saying what had to be true to pass them.

A criterion that cannot be checked is prose. Each one below is written to be answered yes or no by someone who was not in the room.

---

## Phase 1 - Ideation & Strategy

```
Business Stakeholder (01)
  │
  │  Problem statement / idea brief
  ▼
Product Manager (02)
  │
  │  PRD (back to Stakeholder for approval)
  ▼
Business Stakeholder (01)  ──── Approved PRD ────►  Product Manager (02)
```

The Business Stakeholder originates every initiative. The PM (product manager) shapes it into a PRD (product requirements document) and returns it for sign-off before any downstream work begins. Nothing proceeds without an approved PRD.

**Phase 1 exit criteria (all must be true before Phase 2 begins):**
- `01-project-charter.md` exists and states the **problem**, not a chosen solution
- At least one success criterion carries a **number and a unit**. "Better performance" is not a criterion.
- The out-of-scope list is **non-empty**. A scope with no exclusions has not been scoped.
- Stakeholder approval is **recorded with a date**, never inferred from silence

---

## Phase 2 - Requirements & Research

```
Product Manager (02)
  │
  ├── PRD ──────────────────────────────────────────► Business Analyst (03)
  │                                                        │
  │                                                        │  User stories + ACs
  │                                                        ▼
  │                                               Product Manager (02)
  │                                               [reviews & approves stories]
  │
  └── Research brief ───────────────────────────► UX Researcher (04)
                                                        │
                                                        │  Personas, journey maps,
                                                        │  usability findings
                                                        ▼
                                               Product Manager (02)
                                               UX/UI Designer (05)
                                               Business Analyst (03)
```

The BA (business analyst) breaks the PRD into testable user stories with ACs (acceptance criteria), and the PM reviews and approves them before sprint commitment. The UX (user experience) Researcher runs in parallel and informs both design and requirements.

**Phase 2 exit criteria (all must be true before Phase 5 begins):**
- Every user story has acceptance criteria a tester could execute **without asking a question**
- Every open question the BA raised is answered, or **deferred with a named owner**, never left blank
- Research findings **validate or refute each stated hypothesis**. "Inconclusive" must say what would settle it.
- Every requirement traces to a PRD line, and every PRD line traces to at least one requirement

---

## Phase 3 - Architecture & Security (Security runs in parallel with Phase 2; the Software Architect starts after Security and the BA finish)

```
Product Manager (02)  ──── PRD ────►  Security Architect (07)
                                             │
                                             │  Threat model
                                             │  Security requirements
                                             ▼
                                      Software Architect (06)
                                             │
                                             │  Pre-Implementation Challenge [INTERNAL GATE]
                                             │  Validate problem statement, challenge assumptions,
                                             │  identify scaling risks, propose simpler alternatives.
                                             │  Log outcome to 09-decision-log.md before proceeding.
                                             │
                                             │  System architecture
                                             │  API contracts
                                             │  Data model
                                             │  ADRs
                                             ▼
                                      All Engineers (08–11)
```

Security runs threat modeling before the architecture is final. The Software Architect runs the Pre-Implementation Challenge before producing any architecture artifact, to validate the problem statement and rule out complexity nobody needs. The architect then builds in the security requirements and publishes the blueprint the engineers implement against. No significant architecture decision is final without Security Architect review.

**Phase 3 exit criteria (all must be true before Phase 5 begins):**
- The threat model covers **every trust boundary the architecture names**. The two counts match.
- Every security requirement maps to **at least one architectural control**, named
- API contracts are machine-readable and **parse** (the OpenAPI spec validates, not just exists)
- Every decision that forecloses a future option is in `04-architecture-decision-records.md` (the ADRs, architecture decision records) **with its rejected alternatives**

---

## Phase 4 - Design (Backend 08 and DevOps 11 run ‖, since neither consumes a design artifact)

```
UX Researcher (04)  ──── Research findings ────►  UX/UI Designer (05)
Product Manager (02)  ── PRD / feature brief ──►  UX/UI Designer (05)
Business Analyst (03)  ─ Functional specs ──────►  UX/UI Designer (05)
Security Architect (07)  ─ Security requirements ►  UX/UI Designer (05)
                                                          │
                                                          │  Wireframes (→ Stakeholder review)
                                                          │  High-fidelity mockups
                                                          │  Design specs + accessibility annotations
                                                          ▼
                                                  Frontend Engineer (09)
                                                  Mobile Engineer (10)
                                                  QA Engineer (13)
```

The design gates are (1) a low-fidelity review with the PM and the Stakeholder and (2) the high-fidelity handoff to engineering. Usability testing on prototypes feeds back into design before development begins.

**This phase does not gate Backend or DevOps.** The exit criteria below have always said so by naming Frontend and Mobile. It was the phase numbering that gated all of Phase 5. Phase 5's own diagram shows it: the Backend Engineer (08) consumes architecture and API contracts (Phase 3), functional specs (Phase 2) and security requirements (Phase 3), and **nothing from Phase 4**. The DevOps Engineer (11) consumes no design artifact at all. It provides the pipeline and environments the others deploy into throughout Phase 5. This is notation only: the 8 phases stay 8 and nothing is merged.

**Phase 4 exit criteria (all must be true before Frontend or Mobile engineering begins):**
- Every screen in the PRD has a high-fidelity design **or an explicit "not in this release"**
- Empty, loading and error states are specified, **not just the happy path**
- Accessibility annotations are present on **every interactive element**
- Design specs name real tokens and values. **"Match the mockup" is not a spec.**

---

## Phase 5 - Engineering (Backend 08 + DevOps 11 ‖ Phase 4)

```
                          Engineering Manager (17) - Challenge Gate [INTERNAL GATE]
                          Interrogate scope, challenge bad decisions, identify scaling risks,
                          force prioritization. Log pre-implementation decision record to
                          09-decision-log.md. No engineering agents spawn until gate is logged.
                                                │
                                                │  Approved scope + constraints
                                                ▼
Software Architect (06)  ─── Architecture / API contracts ───►  Backend Engineer (08)
Business Analyst (03)  ───── Functional specs ────────────────►  Backend Engineer (08)
Security Architect (07)  ─── Security requirements ───────────►  Backend Engineer (08)
                                                                       │
                                                                       │  Implemented APIs
                                                                       │  Database migrations
                                                                       ▼
UX/UI Designer (05)  ──── Design specs ───────────────────────►  Frontend Engineer (09)
Backend Engineer (08)  ── API contracts ──────────────────────►  Frontend Engineer (09)
                                                                       │
                                                                       │  Implemented UI
                                                                       ▼
UX/UI Designer (05)  ──── Mobile designs ─────────────────────►  Mobile Engineer (10)
Backend Engineer (08)  ── API contracts ──────────────────────►  Mobile Engineer (10)
```

The Engineering Manager challenge gate fires before any engineer is spawned. It is the internal approval that the scope is right before the team commits capacity. Backend and Frontend/Mobile engineering then run in parallel once the API contracts are published. **Backend (08) and DevOps (11) are not gated on Phase 4.** They can start as soon as the challenge gate is logged, because their inputs come from Phases 2 and 3. Frontend (09) and Mobile (10) are the two that wait on design specs. The DevOps Engineer (11) provides the CI/CD (continuous integration and delivery) pipeline, the DORA (DevOps Research and Assessment) metric instrumentation and the environments that all engineers deploy into during this phase.

**Phase 5 exit criteria (all must be true before Phase 6 begins):**
- All pages load without JS errors when served over HTTP (not `file://`)
- Zero 404s in the browser Network tab across all pages
- All `<img>` src attributes and JS template literal image paths resolve to existing files
- Image placeholder filenames derived from actual data files (e.g., JSON slugs), not planning memory
- A `serve.sh` or equivalent local server command exists and is documented
- Security lint gate (`tests/automated/lint-security.sh` or equivalent) exits 0

---

## Phase 6 - Quality Assurance

```
Backend Engineer (08)  ──┐
Frontend Engineer (09)  ─┤  Implemented features (deployed to test env)
Mobile Engineer (10)  ───┘
                               │
                               ▼
                          QA Lead (12)  ──────────────────────────────┐
                               │                                       │
                               ├──── Test plan ──────►  QA Automation Engineer (13)
                               │                                       │  Automated suites
                               │                                       │  Contract tests
                               │                                       ▼
                               └──── Test plan ──────►  Manual Tester (14)
                                                                       │
                                                                       │  Exploratory findings
                                                                       │  Acceptance test results
                                                                       ▼
                                                          QA Lead (12)
                                                          [release readiness sign-off]
```

QA (quality assurance) is not only a final gate. The QA Lead takes part from requirements review onward. Sign-off is issued only when every defined quality gate is met. Defects route back to the engineer who wrote the code.

**Phase 6 exit criteria (all must be true before Phase 7 begins):**
- Every Phase 2 acceptance criterion maps to **at least one executed test**. The traceability matrix has no blanks.
- Zero open severity-1 or severity-2 defects; every severity-3+ carries a **recorded accept-or-defer decision with an owner**
- The automated suite runs green **from a clean checkout**, not only where it was written
- Exploratory testing has been run and its findings recorded **even when it found nothing**. A silent pass cannot be told apart from a skipped one.

---

## Phase 7 - Release & Deployment

```
QA Lead (12)  ──── Release readiness sign-off ───────────►  Release Manager (15)
Product Manager (02)  ── Go/no-go decision ─────────────►  Release Manager (15)
Business Stakeholder (01)  ─ Go/no-go authorization ────►  Release Manager (15)
DevOps Engineer (11)  ─── Build artifacts + runbook ────►  Release Manager (15)
                                                                   │
                                                                   │  Release runbook
                                                                   │  Release communications
                                                                   ▼
                                                          DevOps Engineer (11)
                                                          [executes deployment]
                                                                   │
                                                                   ▼
                                                   Systems Administrator (16)
                                                   [monitors production post-deploy]
```

No deployment proceeds without QA sign-off and the PM/Stakeholder go/no-go. The Release Manager coordinates the sequence, DevOps executes it, and the Sysadmin owns production health from the moment the deployment lands.

**Phase 7 exit criteria (all must be true before the deployment is called done):**
- Rollback has been **executed at least once** in a non-production environment. A documented rollback is not a tested one.
- The runbook names **who executes each step**, as a person, not as a role in general
- Release notes say what changed **for a user**, not what changed in the code
- Monitoring and alerting for the new surface exist **before** the deploy, not after the first incident

---

## Phase 8 - Production Operations

```
Systems Administrator (16)
  │  SLA/SLO reporting
  │  Patch and vulnerability remediation
  │
  │  On incident:
  │
  │  Step 1 - Triage + Debug Context Package
  │  Systems Administrator produces: incident timeline, correlated signals,
  │  blast radius, infrastructure ruling, active mitigations.
  │  Delivers to Backend Engineer before investigation begins.
  │                                          │
  │                                          ▼
  │                               Backend Engineer (08)
  │                               Step 2 - Production Debugging
  │                               5-step protocol: understand code → trace root cause →
  │                               explain failure → enumerate edge cases → fix.
  │                               Produces: Debug Report (5-part) → fix + test.
  │                                          │
  │                                          ▼
  │                               Systems Administrator (16)
  │                               Step 3 - Post-Mortem authorship
  │                               (Backend Engineer authors if app-layer root cause)
  │
  ▼
Engineering Manager (17)  ──  Engineering health report  ──►  Business Stakeholder (01)
```

After launch, the loop closes back to the Stakeholder through the Engineering Manager's health reporting. SLA/SLO are the service level agreement and service level objective. Incidents follow a mandatory two-agent sequence: the Sysadmin delivers the Debug Context Package first, and the Backend Engineer starts investigating only after receiving it. Post-mortems feed lessons back to the Security Architect (for security incidents) and the Software Architect (for reliability improvements).

**Phase 8 exit criteria (per incident; the phase does not end, incidents do):**
- A post-mortem exists for every severity-1, with the root cause stated **in one sentence**
- Every post-mortem action has an **owner and a date**, or is explicitly declined with a reason
- The fix carries a **regression test**, or the post-mortem states why one is not possible
- Feedback to the Security Architect and Software Architect is **delivered and acknowledged**, not merely noted

---

## Coordination Layer (runs across all phases)

```
Business Stakeholder (01)
        │
        │  program oversight, go/no-go decisions
        ▼
Engineering Manager (17)  ◄──────────────────────────────┐
        │                                                  │
        │  delivery oversight, team health, risk escalation│
        ▼                                                  │
Scrum Master (18)  ──── sprint cadence ────►  All Engineers + QA
        │
        │  velocity, impediments, sprint health
        ▼
Project Manager (19)  ──── master plan, risk register, status reports ────►  Business Stakeholder (01)
```

The Engineering Manager, Scrum Master and Project Manager run continuously across every delivery phase. They do not produce features. Their job is to keep the people who do from being blocked.

---

## Summary Flow (one line per phase)

| Phase | Flow |
|:---|:---|
| 1 - Ideation | Stakeholder → PM (PRD) → Stakeholder (approval) |
| 2 - Requirements | PM → BA (user stories) + UX Researcher (personas, research) |
| 3 - Architecture | PM → Security Architect (threat model) → Software Architect (challenge gate → blueprint) → Engineers |
| 4 - Design | UX Researcher + PM + BA + Security → UX/UI Designer → Engineers + QA |
| 5 - Engineering | EM (challenge gate) → Architect + BA + Security → Backend → Frontend / Mobile (parallel) |
| 6 - QA | All Engineers → QA Lead → QA Auto + Manual Testers → QA Lead (sign-off) |
| 7 - Release | QA + PM + Stakeholder → Release Manager → DevOps → Sysadmin |
| 8 - Operations | Sysadmin (Debug Context Package) → Backend Engineer (Debug Report) → Sysadmin (post-mortem) → EM → Stakeholder |
| Continuous | EM + Scrum Master + PM coordinate delivery across all phases |
