# Frameworks

The prompts and workflows elsewhere in this repo answer "how do I do this piece of work well." These
answer the question underneath that one: **which work should AI be touching at all, who does it, and
where does the human stay.**

Built and used on real programs by [Eric White](https://www.linkedin.com/in/edwhite/). Same standard
as the rest of the repo: written down because it was used often enough to be worth writing down.

---

| Framework | Answers |
|---|---|
| [AI Execution Tiers](ai-execution-tiers.md) | How much AI belongs in a given activity, on a five-tier scale from human-only to AI-only, and how to classify without kidding yourself |
| [Activity Mapping Method](activity-mapping-method.md) | How to map an entire company's work against those tiers in about a week, at three levels of resolution |
| [Multi-Agent Delivery Framework](multi-agent-delivery-framework.md) | 19 roles across 8 phases, ideation through operations, with senior/junior tier selection and an audit trail |
| [AI Tool Decision Matrix](ai-tool-decision-matrix.md) | What to buy and in what order, and why the AI layer is phase 4 of 5 |

Regulated environments (HIPAA, SOC 2, PHI) change the adoption order. That overlay lives in
[security-program-playbooks](https://github.com/ChefPlex/security-program-playbooks).

---

## Where this sits relative to the AI governance standards

**This is not a standard and it does not replace one.** It is an operational framework: it answers
*where AI belongs in the work, who does it, and where the human stays.* The standards answer a
different question - *how do you govern AI risk across an organization and prove that you did.*
Both questions are real and the answers are not substitutes for each other.

The landscape as of **August 2026**, in four layers. It is moving quickly and this is a map, not a
compliance reference.

### Management and process standards - the ISO/IEC family

**42001 is the one people name, and it does not stand alone.** It sits in a family where each part
answers a different question, and knowing the shape is more useful than knowing any one of them:

| Standard | Answers |
|---|---|
| **ISO/IEC 42001:2023** | Does the organization have an AI management system? **Certifiable** - third-party audit, formal certificate |
| **ISO/IEC 23894** | How do you actually run AI risk management? The technical companion to 42001's risk requirements |
| **ISO/IEC 42005** | What impact does this specific AI system have on people, society and the environment? Impact assessment methodology, **not certifiable** |
| **ISO/IEC 22989** | What do the words mean? The vocabulary standard, so governance, risk, engineering and vendors are describing the same things |
| **ISO/IEC 5338** | What does the AI system lifecycle look like as a set of processes? |
| **ISO/IEC 38507** | What does a board need to understand and decide? Governance-body guidance, above the management system |

### Risk frameworks - voluntary

- **NIST AI Risk Management Framework** - a US risk-function framework, widely referenced well
  outside the US. Its **Generative AI Profile (AI 600-1, July 2024)** sets out 12 risk categories
  specific to generative systems.

### Binding regulation

- **EU AI Act** - the first comprehensive risk-based AI regulation. GPAI obligations took effect
  2 August 2025; **Commission enforcement and the Article 50 transparency obligations began
  2 August 2026.** Mandatory within EU scope, with amendments under negotiation.
- **A US state patchwork, changing fast.** Several states now have AI statutes with different
  scopes and different effective dates, and at least one has already been narrowed after passage.
  ⚠️ **This is the layer most likely to be out of date in any document you read, including this
  one.** Do not plan against a summary; check the current text for the states you operate in.

### Intergovernmental and soft law

Non-binding, but they shape the ones above and get cited in procurement:

- **OECD AI Principles** - first intergovernmental AI standard, adopted 2019 and updated 2024, with
  49 adherents as of April 2026. Five values-based principles.
- **UNESCO Recommendation on the Ethics of AI** - adopted 2021, applicable across all 194 member
  states, framed around the full system lifecycle.
- **Council of Europe Framework Convention on AI and human rights, democracy and the rule of law** -
  applies existing human-rights obligations to AI activity.

⚖️ **One point of contact is worth knowing about, because it lands on tier 4.** The Act's Article 50
transparency rules do **not** cover every use of AI - the scope is disclosure when someone is
interacting with an AI system, deepfakes, and AI-generated text published to inform the public on
matters of public interest. **The labelling obligation is lifted where content has had human review
or editorial control with a named person holding editorial responsibility, and that review must be
substantive rather than cursory approval.**

**That is the same distinction the tier model already draws** between a real tier-4 gate and one
that has degraded into a rubber stamp - see
[AI Execution Tiers](ai-execution-tiers.md#tier-4---ai-drives--humans-review). It is not legal
advice and the obligations are moving; the structural point is that **the honesty of a human-review
gate may now have to be demonstrated rather than asserted.**

They are generally treated as **complementary rather than competing** - management-system framing,
risk-function structure, and binding legal requirements respectively - and larger organizations
commonly operate under more than one at the same time.

**What that means for this framework:** the tiers, the activity map and the delivery model sit
*underneath* whichever of those apply to you. A tier assignment is an operational decision about
how a specific activity gets done. It is not a risk classification, it is not a conformity
assessment, and it will not satisfy an auditor on its own. ⚠️ **If you are subject to any of the
above, treat this as the layer that describes what your organization actually does, and the
standard as the layer that says what you must be able to demonstrate.**

⛔ **This document claims no expertise in any of them.** It records that they exist, that they are
maturing, and that anyone building an AI operating model in 2026 should know they are there.
**Dates and obligations move** - the EU AI Act has amendments under negotiation and the US state
picture has already shifted once - so verify current status against the source rather than against
this page.

🔑 **The one structural observation worth taking from the layers above:** almost all of it governs
**risk and accountability** - what could go wrong, who is answerable, what you must be able to
demonstrate. **Very little of it addresses how the work gets divided between people and machines in
the first place.** That gap is what these frameworks are for. It is also why they cannot substitute
for a standard, and why a standard will not tell you which activities to hand over.

---

## The through-line

All four documents are one argument, and it is the same one this repo opens with: **the tools are
not about replacing judgment, they are about removing mechanical work so there is more time for the
work that actually requires it.**

The execution tiers make that concrete by forcing every activity onto exactly one rung, in writing,
with a named owner. The mapping method is how you produce that map. The delivery framework is what
it looks like when the approach is built out fully for one function. The tool matrix is what to buy
once you know where the work is.

Read in that order if you are starting from nothing. Start with the tool matrix if someone has
already bought the license and is asking why nothing improved.

**A human is always in the loop.** They edit, they approve, and they stay part of the solution. What
moves across the tiers is where they stand, never whether they are there.
