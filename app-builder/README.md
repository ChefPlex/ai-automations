# App Builder

A two-prompt workflow for going from a rough app idea to a working web application. The first prompt interviews a non-technical person and produces a structured brief. The second takes that brief and guides a developer through building the actual app, phase by phase.

The two prompts are designed to hand off to each other - but each also works independently.

---

## The Two-Prompt System

### Prompt 1: App Idea Intake

`app-idea-intake-prompt.md`

For the person with the idea who is not a developer. Paste it into Claude, answer the questions, receive a structured brief with an Idea Summary (written for them) and Developer Notes (written for the developer).

The conversation covers: the problem, the user, the core experience, existing alternatives, the business model, the definition of success, and any open concerns. One question at a time, takes about 10 minutes.

### Prompt 2: Web App Builder

`web-app-builder-prompt.md`

For the developer who is building the app. Six phases: idea refinement, tech stack selection, architecture and data model, MVP feature scope, UI/UX design direction, and feature-by-feature build. Each phase produces a concrete output before moving to the next.

Designed for someone with a scripting or Unix background who learns by doing. Produces complete, copy-paste-ready code at every step - no placeholders.

---

## The Handoff

```
Non-technical person with an idea
         ↓
Runs App Idea Intake Prompt (~10 min conversation)
         ↓
Sends Developer Notes to developer
         ↓
Developer pastes Developer Notes into [DESCRIBE YOUR IDEA]
in the Web App Builder Prompt
         ↓
Builder starts Phase 1 already half done
```

Without the intake prompt, the developer fills in their own 2-5 sentence description and Phase 1 does the full discovery work. Both paths work. The two-prompt path produces a better Phase 1 outcome because the non-technical person surfaces constraints, use cases, and competitive context that a developer writing alone tends to skip.

---

## Files

| File | Who Uses It | When |
|------|------------|------|
| `app-idea-intake-prompt.md` | Non-technical person with an idea | Before the developer starts |
| `web-app-builder-prompt.md` | Developer building the app | After the idea is clear |

---

## How to Run Each Prompt

Both prompts work the same way:

1. Open a new Claude chat at claude.ai
2. Copy the prompt text from between the triple backtick fences in the markdown file
3. Fill in any placeholders (the builder prompt has one: `[DESCRIBE YOUR IDEA]`)
4. Paste and send
5. Follow the conversation

Neither prompt requires a Claude account with special features. The builder prompt's Phase 5 UI output works best in Claude.ai with artifacts enabled, but all other phases work in any interface.

---

## What the Builder Produces

By the end of a full builder session:

- A confirmed product brief
- An approved tech stack with rationale
- A system architecture diagram and data model
- A prioritized MVP feature checklist
- A visual design direction with colors, fonts, and layout
- Working code for the first screen
- Feature-by-feature working code for the full v1 build

The session is stateful - each phase builds on the previous one. Keep the conversation going rather than starting a new chat between phases.

---

## Design Notes

**Why one question at a time in the intake prompt:** Most people with app ideas have never had to articulate them in a structured way. A list of questions produces vague answers. A conversation surfaces things the person did not know they knew - constraints, edge cases, competitive context. The one-at-a-time approach takes longer but produces a substantially better Developer Notes output.

**Why six phases in the builder prompt:** The most common failure mode for beginner developers is starting to code before the idea is clear, the stack is chosen, and the scope is bounded. The phase structure prevents scope expansion and context switching. Skipping phases is how projects stall at 70%.

**Why complete code only:** Prompts that produce placeholder comments are useless for someone learning by doing. The builder prompt explicitly prohibits them and asks for complete, copy-paste-ready code at every step.

**Why one stack recommendation, not options:** Beginners do not benefit from "you could use X or Y." They need a decision with a reason. The builder prompt asks Claude to make the call and explain it simply.

---

*Part of the [ai-automations](https://github.com/ChefPlex/ai-automations) repo. Built by [Eric White](https://github.com/ChefPlex).*
