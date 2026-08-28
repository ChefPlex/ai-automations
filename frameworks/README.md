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

Three bodies of work anchor the space as of **August 2026**, and they are maturing quickly:

| | What it is | Status |
|---|---|---|
| **ISO/IEC 42001:2023** | A certifiable international management-system standard for AI - the structures and processes an organization needs to govern AI responsibly | Voluntary, certifiable |
| **NIST AI Risk Management Framework** | A voluntary US risk-function framework, with a Generative AI Profile (AI 600-1, July 2024) covering 12 risk categories | Voluntary |
| **EU AI Act** | The first comprehensive risk-based AI regulation. GPAI obligations took effect 2 August 2025; **European Commission enforcement began 2 August 2026** | Mandatory within EU scope |

They are generally treated as **complementary rather than competing** - management-system framing,
risk-function structure, and binding legal requirements respectively - and larger organizations
commonly operate under more than one at the same time.

**What that means for this framework:** the tiers, the activity map and the delivery model sit
*underneath* whichever of those apply to you. A tier assignment is an operational decision about
how a specific activity gets done. It is not a risk classification, it is not a conformity
assessment, and it will not satisfy an auditor on its own. ⚠️ **If you are subject to any of the
above, treat this as the layer that describes what your organization actually does, and the
standard as the layer that says what you must be able to demonstrate.**

⛔ **This document does not claim expertise in any of them.** It notes that they exist, that they
are getting better, and that anyone building an AI operating model in 2026 should know they are
there. **Dates and obligations move** - the EU AI Act in particular has amendments under
negotiation - so verify current status against the source rather than against this table.

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
