# Pre-Meeting Brief Prompt

## Use this when

A steering committee, executive review, or cross-org decision meeting is coming and you need to walk in knowing who wants what, which decisions actually have to land, and where the meeting is likely to go sideways.

## Why it matters

Most decision meetings fail before they start. The agenda says "discuss the roadmap" and nobody knows what is being decided, so the hour produces alignment theater and one more meeting. The work is not summarizing the agenda. It is predicting the room: what each person will push on, which decisions can realistically close, and what you need in hand when the hard question arrives.

The prediction is the point. A brief that only restates the agenda saves you nothing.

## Inputs to gather

- Agenda, or the topics if there is no formal agenda
- Participant list with roles and what each owns
- Decisions that need to land in this meeting
- Current program state: status, slipping items, open risks
- What happened last time, and anything promised at that meeting
- Known tensions, disagreements, or unresolved history between participants
- Time available, and how much of it is realistically yours

## Prompt

```text
Help me prepare for the meeting described below.

Produce a one-page brief with these sections:

1. THE ONE THING. If only one outcome is possible in the time available,
   what should it be, and what has to be true for it to close.

2. PER PARTICIPANT. For each person: what they own, what they most likely
   care about here, what they are likely to push on, and what they need
   from me to say yes.

3. DECISIONS NEEDED. For each: the actual question, who decides, what the
   options are, and my recommendation. Mark any decision that cannot close
   because information or an absent decision-maker is missing.

4. LIKELY OBJECTIONS. The three most probable challenges, with the factual
   answer to each. Include the objection I would least like to be asked.

5. WHAT TO HAVE READY. Specific numbers, documents, or evidence to have on
   hand, tied to the objection or decision each supports.

6. WHAT NOT TO RAISE. Topics that will consume the hour without closing,
   and where each belongs instead.

Rules:
- Be specific. "They care about timeline" is useless; name which date and
  why it matters to them.
- Do not invent stakeholder positions. If the context does not support a
  read on someone, say "insufficient context" and name what would resolve it.
- Separate what I know from what I am assuming. Label assumptions.
- If a decision cannot land in this meeting, say so plainly rather than
  producing a plan that pretends it can.

Context:
[paste sanitized context]
```

## Expected output

- The one outcome worth protecting
- A per-participant read with the likely push and the required ask
- Decisions, with the ones that cannot close flagged
- Three probable objections with factual answers
- A short list of evidence to have ready
- Topics to defer, with their proper home

## Human review checklist

- Every stakeholder read is grounded in something in the context, not in a job title
- Assumptions are labeled as assumptions
- The recommendation on each decision is one you would actually defend
- The uncomfortable objection is genuinely the uncomfortable one, not a soft substitute
- Anything marked "cannot close" says what is missing
- Nothing in the brief asserts a position for an absent person as though it were confirmed

## Data handling notes

Stakeholder reads are inferences about real colleagues. Keep them in the brief and out of anything shared, forwarded, or pasted into a ticket. Remove customer names, commercial terms, security findings, and personnel matters unless the audience is already approved for them. Never characterize a named individual in a document that could travel.

## Done when

You can state the one outcome that matters, name what each person needs to say yes, and answer the question you least want to be asked without looking anything up.
