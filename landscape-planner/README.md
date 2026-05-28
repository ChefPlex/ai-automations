# Landscape Planner

A two-file AI workflow that acts as a knowledgeable landscape architect for Sonoma County, California. Give it your budget, yard situation, and goals. Get back a visual layout, a phased implementation guide, a plant shopping list, and a budget breakdown.

Built for wine country conditions: Mediterranean climate, fire safety requirements, deer, gophers, and the 32-inch rainy season that only runs November through March.

---

## What It Does

You load the persona and prompt files into Claude, answer a series of questions about your yard, and receive three deliverables:

- **On-screen summary** - Priorities, top recommendations, and next steps
- **Visual yard plan** - Bird's-eye sketch of the proposed layout with labeled zones and planting areas
- **Complete implementation guide** - Phased, step-by-step instruction doc with local nursery recommendations, budget breakdown, plant shopping list, and seasonal maintenance calendar

The consultation covers budget, maintenance tolerance, water philosophy, wildlife pressure (deer and gophers are a given in Sonoma County), fire safety, sun and soil conditions, style preferences, and any special requirements.

---

## Files

| File | Purpose |
|------|---------|
| `landscape-architect-persona.md` | Jordan Miller's background, plant knowledge, local expertise, and design philosophy. Load this as reference context. |
| `yard-planning-prompt.md` | The consultation workflow: discovery questions, output format, seasonal guidance, and budget-based tuning. Load this as the system prompt or primary instruction. |

---

## How to Use

### In Claude.ai

1. Start a new conversation
2. Upload both files as attachments
3. Tell Claude: "You are Jordan Miller. Use the persona file for background knowledge and the prompt file to run the consultation. Start by greeting me and asking about my budget."
4. Answer the questions one at a time
5. Receive your three deliverables

The visual yard plan generates as an artifact (SVG or canvas) when run in Claude.ai. In other interfaces it produces a detailed text-based layout description instead.

### In Claude Code or API

Load `landscape-architect-persona.md` as system context and `yard-planning-prompt.md` as the user-facing instruction. The persona gives Claude the domain knowledge; the prompt drives the conversation and output format.

```python
system_prompt = open("landscape-architect-persona.md").read()
user_prompt = open("yard-planning-prompt.md").read()
# Then run your consultation loop
```

---

## What It Knows

**Climate and timing:** Zone 9b, Mediterranean growing conditions, fall planting advocacy, summer heat warnings. It will tell you not to buy plants in May and explain exactly why.

**Local resources:** King's Nursery, Laguna Foundation native plant sales, Sonoma County Water Agency WaterSmart rebates, Japanese Maples by Momiji, Ancient Olive Trees.

**Fire safety:** Post-2017 Tubbs Fire defensible space requirements, Zone 0 and Zone 1 design, ember-resistant plant selection.

**Wildlife reality:** Deer-resistant strategies, gopher exclusion methods, honest assessments of what "deer-resistant" actually means in practice.

**Budget tiers:** Separate guidance for under $3K (heavy DIY), $3K-10K (mixed), and $10K+ (professional installation options). Phasing strategies for stretching any budget.

---

## Adapting This Pattern

This workflow demonstrates a reusable AI prompt architecture: a **persona file** that carries stable domain knowledge separately from a **prompt file** that drives the session interaction. The persona is reusable across different prompt types; the prompt can be swapped for different consultation formats without rewriting the expertise.

The same pattern works for other domain-expert personas: a security incident responder, a compliance analyst, a program kickoff facilitator. Separate what the expert knows from how the session runs.

---

## Note on Visualization

Image generation in the visual yard plan step works when running in Claude.ai with artifacts enabled. In API calls or CLI contexts, the output is a detailed text layout description instead. The rest of the consultation - the summary, the implementation guide, the plant list - works in any interface.

---

*Part of the [ai-automations](https://github.com/ChefPlex/ai-automations) repo. Built by [Eric White](https://github.com/ChefPlex).*
