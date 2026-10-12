# The Five Execution Tiers

## What this is for

**The point is not to replace people. It's to make them more effective, and to give them back the
time that mechanical work was taking.**

That's not a disclaimer at the front of a document that goes on to argue the opposite. It is the
design constraint, and it decides what the tiers are allowed to say. A model built to remove
headcount would push every activity as far down the ladder as it would go and treat tier 5 as the
finish line. This one does not. **The tiers exist to find the work that was never worth a person's
attention, so that the person can go do the work that's** - the judgment, the relationships, the
decisions with consequences, the problems nobody has specified yet.

**A human is always in the loop.** They edit, they approve, and they remain part of the solution.
What changes across the five tiers isn't *whether* a human is involved but *where they're
standing* - authoring the work, directing it, approving each item, or owning a system that runs.

The whole model then rests on one move: **every activity gets exactly one tier, in writing.**

Not a range. Not "depends." One tier, one owner, one tool. The moment you allow "it depends,"
you have recreated the ambiguity the exercise exists to remove.

---

## Tier 1 - Human-only execution

**A human does this, alone. No AI in the loop, by decision rather than by neglect.**

Use it when the activity carries one of:

- **Accountability that can't be delegated.** A go/no-go release decision, an incident severity
  call, an offer approval. Someone's name is on it.
- **Judgment built on context the model doesn't have.** Architecture tradeoffs that hinge on what
  the team can actually maintain. Compensation decisions that hinge on a person's last eighteen months.
- **Relationship as the substance of the work.** Investor conversations. Negotiating key contract
  terms. A difficult conversation with a struggling employee.

⚠️ **This tier is the one people quietly skip, and skipping it is the single most expensive mistake
in the model.** A framework with no tier 1 is a framework that will eventually recommend automating
a firing. Populate this tier first, deliberately, before you classify anything else - it's much
easier to defend a boundary you drew before you knew what it would cost you.

---

## Tier 2 - Humans drive / AI speeds up

**The human does the work and owns the output. AI removes friction from the mechanical parts.**

The human would still produce this without AI - just slower. AI is doing retrieval, formatting,
first-pass structuring, boilerplate.

Examples: a security architect running a threat-model session with AI mapping the attack surface
from existing diagrams; an engineer implementing a feature with an AI editor; a manager
interrogating a scope proposal with AI surfacing the scaling risks.

**The test:** if the AI vanished, would the work still get done to the same standard? If yes, and
it would just take longer, it is tier 2.

---

## Tier 3 - Humans ideate / AI creates

**The human decides what should exist and what "good" means. AI produces the artifact.**

This is the tier most knowledge work lands in, and the tier most often mislabeled as tier 4.

Examples: drafting a PRD from a brief; generating an ERD from a functional spec; writing release
notes from a git log; drafting a post-mortem timeline from logs and traces.

**The distinction from tier 4 is who initiates.** In tier 3 a human decides the artifact should
exist and sets the frame. The AI fills it. Nothing happens unless a human starts it.

---

## Tier 4 - AI drives / Humans review

**AI initiates and produces. A human approves before it takes effect.**

The AI is deciding *that* the work should happen, not only *how*. The human gate is real - it can
stop the output - but it's reviewing a finished thing rather than commissioning one.

Examples: automated PR review that drafts comments for a person to post; a vulnerability scanner
opening tickets for critical CVEs; lead scoring routing prospects to a pipeline; anomaly detection
paging an on-call engineer.

Note the first example. An automated review that *posts* its comments has no gate before the
effect - posting is the effect - so it is tier 5, whatever the process document says. It becomes
tier 4 only when the comments are drafts and a named person decides what gets posted.

🔴 **This is where the discipline is.** Tier 4 fails in a specific and predictable way: **the review
degrades into a rubber stamp.** It happens gradually, it happens to good teams, and it happens
fastest when the AI is mostly right - because being mostly right is exactly what trains a reviewer
to stop reading.

Four things keep a tier-4 gate real, and they are cheap:

1. **The reviewer must be able to say no cheaply.** If rejecting means redoing the work by hand,
   they will approve. Build the path back.
2. **Seed known-bad items and measure the catch rate.** A rejection rate alone cannot tell a good
   generator from a rubber stamp: a 0% rejection rate looks the same either way. Slip in items you
   know are wrong and count how many the reviewer stops. A gate that misses the seeded items is not a
   gate. It is a log. Either promote the activity to tier 5 honestly, or find out why review stopped.
3. **Keep the ask rate low.** A gate that fires on everything stops being reviewed. Route only the
   items that need a person through the gate, so each one gets real attention.
4. **Name the reviewer, not the team.** "Engineering reviews it" means nobody reviews it.

### In EU scope, a rotted tier-4 gate now has a legal consequence

**This stopped being purely an operational concern on 2 August 2026**, when the EU AI Act's
Article 50 transparency obligations took effect.

Article 50 does **not** require disclosing every use of AI. Its scope is specific: telling people
when they're interacting with an AI system, labelling deepfakes, and labelling AI-generated or
manipulated **text published to inform the public on matters of public interest.**

🔑 **What matters here is the carve-out.** The labelling obligation doesn't apply where the content
**has undergone human review or editorial control and a named person or organization holds editorial
responsibility** - and the guidance is explicit that such review must be **substantive, not limited
to superficial matters or cursory approval.**

Read that against the failure mode above:

- **A tier-4 gate doing real review is the exemption.** A human with named editorial responsibility
  is reviewing before publication, which is precisely what the carve-out describes.
- **A tier-4 gate that has rotted into a rubber stamp is "cursory approval"** - the thing the
  guidance names as insufficient. The activity is then operating as tier 5 while being documented
  as tier 4, and the exemption it was relying on may not hold.

**So the catch-rate measurement above isn't only hygiene.** In EU scope it's the difference
between a defensible position and a claimed exemption you cannot evidence. **And "name the reviewer,
not the team" turns out to match the law's own requirement for a natural or legal person holding
editorial responsibility.**

⚠️ **This is a framework note, not legal advice, and it's a moving target** - the Act has since
been amended by the Digital Omnibus on AI (Regulation (EU) 2026/1744 of 8 July 2026), which among
other changes gives providers whose systems were already on the market a transitional period for
the marking obligations. **Verify scope and current obligations with counsel** rather than
against this paragraph. The point worth carrying is structural: **the honesty of your human-review
gate is now something you may have to demonstrate, not merely assert.**

---

## Tier 5 - AI-only execution

**No per-item human gate. The activity runs on its own, and humans see the result rather than
approving each instance.**

🔑 **Read that carefully, because the tier name oversells it.** "AI-only" describes the *approval
path*, not the *accountability*. A human still specifies the activity, configures it, owns it,
reads its output in aggregate, and can stop it. What has been removed is the per-item click, not
the person. **There is no tier in this model where nobody is responsible.**

Reserve it for work that's mechanical, where the failure mode is visible, and the blast radius
is bounded.

Examples: log aggregation and indexing; automated regression suites in CI; deploy-frequency metric
emission; scheduled competitor-news collection. Note what these have in common - **none of them is
a decision.** They are collection, execution, and measurement.

**Three conditions, all required, before anything goes to tier 5:**

- **Bounded blast radius.** The worst realistic failure is recoverable and cheap.
- **Visible failure.** If it stops working, someone finds out *without* having to check. An
  automation whose failure is silent is worse than the manual step it replaced - it's the manual
  step, plus false confidence. And a green run proves the output was produced, not that anyone
  read it or acted on it. Name who reads the output and what they do with it.
- **A reason it's not tier 4.** "We got tired of approving it" is a real reason, honestly stated,
  and it's far better than a tier-4 gate everyone has stopped reading. Write it down.

⚠️ **Tier 5 isn't the goal.** The model isn't a maturity ladder to climb. A healthy map has
activities at every tier, and the tier-1 column stays populated permanently. A company whose map
has drifted entirely to tiers 4 and 5 hasn't matured; it has stopped deciding.

---

## "But AI is a clarity engine, not a decision maker"

That principle and this ladder are sometimes read as contradicting each other. They do not, and the
resolution is worth stating plainly because it's the spine of the whole model:

> **The principle governs judgment. The tiers govern labour.**

AI can be handed an enormous amount of *work* - drafting, generating, scanning, testing, executing
a defined runbook - and none of that is a decision. What it is never handed is the call: what
should be built, whether this ships, who gets hired, how much risk is acceptable, what the
architecture forecloses. Those sit at tier 1 and 2 permanently, and they're the reason the other
tiers are safe to use.

**So the ladder isn't a slide from "human" toward "no human."** It's a description of how much
mechanical work a human can put down while keeping every judgment they were actually hired for.
Delegating the labour is what creates the room to do the judgment well.

A multi-agent delivery framework can build the thing. A QA framework can test it. **A human still
edits it, still approves it, and remains part of the solution** - that's not a constraint bolted
onto the model, it is the point of the model.

---

## Classifying: the five questions

For each activity, in order. In questions 1 to 4, the first answer that stops the sequence sets
the tier. Question 5 then checks the result.

1. **Would we accept this decision being made without a human?** No → **tier 1**.
2. **Does a human need to author the substance, or only direct it?** Author → **tier 2**.
   Direct → continue.
3. **Who initiates - human or system?** Human → **tier 3**. System → continue.
4. **Is there a real gate before it takes effect?** Yes → **tier 4**. No → **tier 5**.
5. **Is the effect irreversible or outbound** - a send, a payment, a deletion, a post, a deploy?
   Then it cannot be tier 5, and its tier-4 gate **blocks until approved** and **records who
   approved**. An approval that times out into "go" is not a gate.

**Do this with two people who do the work, not one person who owns the org chart.** The
disagreements are the deliverable. An activity where two practitioners answer question 3
differently is an activity where the process is genuinely undefined, and you've just found it
for the price of a conversation.

---

## What to record

For every activity, four fields. Fewer and the map is decorative; more and nobody maintains it.

| Field | Why |
|---|---|
| **Tier** | The decision |
| **Owner** | A named role. Not a team - a role |
| **Tool** | What actually does the work, named specifically |
| **Gate** | For tiers 4 and 5: who can stop it, or an explicit "nobody, and here is why" |
