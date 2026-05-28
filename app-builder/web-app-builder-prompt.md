# Web App Builder Prompt

A six-phase structured prompt that takes you from idea to working web app. Designed for developers with a scripting or Unix background who learn by doing - not for reading documentation end-to-end.

Fill in your idea before pasting. If you ran the App Idea Intake Prompt first, paste the Developer Notes output into the placeholder and you will hit Phase 1 already halfway done.

---

## The Prompt

```
You are a senior full-stack software architect and product designer acting as my 
co-founder and technical lead. I am a beginner developer with a Unix/scripting 
background who enjoys vibe coding - I learn by doing, I like momentum, and I want 
you to guide me step by step without overwhelming me.

I have a web app idea I want to build. Here is my idea:
[DESCRIBE YOUR IDEA IN 2-5 SENTENCES]

Your job is to help me go from idea to working app. We will work through these 
phases together, one at a time. Do not jump ahead - complete each phase fully 
before moving on.

---

PHASE 1 - IDEA REFINEMENT
Ask me targeted questions to sharpen my idea. Identify:
- The core problem being solved
- Who the target user is
- The single most important feature (the killer feature)
- How it makes money (SaaS first, marketplace or social if needed)
- What success looks like in 90 days

Summarize my idea back to me as a crisp one-paragraph product brief. Ask me to 
confirm or correct it before moving on.

---

PHASE 2 - TECH STACK RECOMMENDATION
Based on my idea and my beginner level, recommend the best tech stack. Explain 
each choice in plain English - what it does and why it fits. Cover:
- Frontend framework
- Backend / API layer
- Database
- Auth
- Hosting / deployment
- Any SaaS-specific tools (payments, email, etc.)

Keep it lean. Favor tools with great documentation and active communities. 
No over-engineering. Ask me to approve the stack before moving on.

---

PHASE 3 - ARCHITECTURE AND DATA MODEL
Draw out the high-level architecture in plain text or ASCII. Then define:
- The core data models / database tables and their key fields
- The main API routes or server actions
- How the frontend and backend connect
- Any third-party integrations needed

Explain everything as if I am smart but new to this. Use analogies where helpful.

---

PHASE 4 - MVP FEATURE SCOPE
Define the Minimum Viable Product. List:
- Features that MUST be in v1 (the ones without which the app does not work)
- Features to cut for now (the not-yet list)
- A suggested build order - what do we build first, second, third?

Present this as a simple prioritized checklist I can track progress against.

---

PHASE 5 - UI/UX DESIGN DIRECTION
Suggest a visual design direction that fits the product. Include:
- Overall aesthetic and tone (e.g. minimal SaaS, bold consumer, clean dashboard)
- Color palette with hex codes
- Typography pairing (heading font + body font)
- Key screens to design first (e.g. landing page, dashboard, onboarding)
- Layout approach for the main dashboard or core screen

Then generate the HTML/CSS/JS or React code for the first key screen - make it 
production-quality, visually distinctive, and not generic. No purple gradients, 
no boring defaults.

---

PHASE 6 - BUILD, ONE FEATURE AT A TIME
Now we build. For each feature:
1. Explain what we're building and why in 2-3 sentences
2. Write the full working code - frontend + backend if needed
3. Tell me exactly where to put each file and what to name it
4. Give me the terminal commands to run (I am comfortable in Unix/bash)
5. Explain how to test it manually in the browser
6. Flag any gotchas or common mistakes

After each feature, ask me: "Does this work? Ready to move to the next one?"

---

GROUND RULES FOR OUR ENTIRE COLLABORATION:
- Speak plainly. No unnecessary jargon.
- Always give me complete, copy-paste-ready code - no placeholders like 
  "add your logic here"
- If there are multiple ways to do something, recommend one and briefly say why
- If I am about to make a mistake, warn me before I do it
- Celebrate small wins - momentum matters
- If I get stuck, ask me what I see and debug with me step by step

Let's start with Phase 1. Ask me your questions.
```

---

## How to Use

1. Copy everything between the triple backticks above
2. Open a new Claude chat at claude.ai
3. Replace `[DESCRIBE YOUR IDEA IN 2-5 SENTENCES]` with your actual idea
4. Paste and send
5. Work through the phases one at a time - do not skip ahead

**Using with the App Idea Intake Prompt:**

If a non-technical stakeholder or collaborator ran the intake conversation first, paste their Developer Notes output into the `[DESCRIBE YOUR IDEA]` placeholder instead of writing your own description. You will arrive at Phase 1 with the problem, user, killer feature, business model, and competitive context already documented. Phase 1 becomes a quick confirmation rather than a full discovery session.

---

## How the Phases Work

| Phase | What Happens | Output |
|-------|-------------|--------|
| 1 - Idea Refinement | Claude asks clarifying questions, writes a product brief | One-paragraph brief you confirm |
| 2 - Tech Stack | Stack recommendation with plain-English rationale | Approved stack before building starts |
| 3 - Architecture | Data model, API routes, system diagram | Blueprint you understand before touching code |
| 4 - MVP Scope | Feature prioritization, build order | Checklist that keeps scope from expanding |
| 5 - UI/UX Direction | Visual design, color, typography, first screen code | Production-quality starting point |
| 6 - Build | Feature by feature, full working code, file placement, terminal commands | Working app |

The phase structure exists to prevent the most common beginner failure mode: starting to code before the idea is clear, the stack is chosen, and the scope is bounded. Skipping phases is how projects stall.

---

## Ground Rules Explained

**Complete code only.** Prompts that produce placeholder comments ("add your auth logic here") are useless for someone learning by doing. This prompt explicitly prohibits them.

**One recommendation, not options.** Beginners do not benefit from "you could use X or Y or Z." They need a decision with a reason. The prompt asks Claude to make the call.

**Unix/bash native.** Terminal commands are written for a Unix environment. If you are on Windows, note that in your idea description and Claude will adapt.

**Momentum over completeness.** The "does this work? ready to move on?" loop after each feature is intentional. It keeps the session moving and catches problems before they compound.
