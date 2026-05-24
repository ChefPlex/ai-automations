# Operating Principles

These principles define how TPMs should use AI in program execution. The short version is simple: use AI to get clearer faster, but do not hand it the judgment.

## 1. AI is a clarity engine, not a decision maker

AI can summarize, structure, rewrite, compare, and point out gaps. It should not make final decisions for program owners, engineering leaders, security leaders, legal teams, product leaders, or executives.

The TPM remains accountable for the final artifact. That includes the facts, the tone, the risk language, the owners, and the decision ask.

## 2. Signal over volume

The best TPM artifacts reduce noise. A good AI-assisted output should make these things easier to find:

- Current status
- What changed
- What is blocked
- What is at risk
- Who owns the next action
- What decision is needed
- What happens if no action is taken

More words are not more clarity. Sometimes they are just a place for risk to hide.

## 3. Separate facts, assumptions, and opinions

Every output should distinguish between:

- Confirmed facts
- Reasonable assumptions
- Open questions
- Recommendations

This is especially important for executive updates, customer escalations, compliance programs, launch readiness reviews, and incident-adjacent work. People can work with uncertainty when it is named clearly. They make bad decisions when uncertainty is polished into confidence.

## 4. Do not polish away risk

AI can make a messy program sound healthier than it is. That is not helpful.

Preferred wording:

```text
The program is Yellow because two service teams have not committed migration dates, and the final validation environment is not available yet.
```

Avoid wording like:

```text
The program is progressing well with minor follow ups remaining.
```

The first version gives leadership something to act on. The second version makes everyone feel better for about five minutes.

## 5. Use AI to improve questions

Strong TPMs use AI to ask better questions, not just to write cleaner updates.

Good questions include:

- What dependency am I missing?
- What risk is hidden in this plan?
- What decision is actually needed?
- Who is the right decision maker?
- What data would change the recommendation?
- What is the cost of waiting?

That last one is often the real escalation.

## 6. Treat AI output as a draft

Every output needs human review for:

- Accuracy
- Tone
- Dates
- Owners
- Risk language
- Customer impact
- Executive asks
- Security and privacy handling
- Alignment with source systems

If the output is going to a VP, customer-facing leader, security leader, legal reviewer, or engineering director, the review bar goes up.

## 7. The system of record still matters

AI summaries do not replace Jira, Salesforce, Google Docs, dashboards, approval records, or decision logs.

After using AI, update the right system of record. The work is not complete until the people and systems that depend on the information can trust it.

## 8. Good automation builds trust

A good AI-assisted workflow should make teams feel more aligned, not more watched.

Use automation to remove manual burden, clarify ownership, and reduce ambiguity. Do not use it to surprise teams with public escalations, unreviewed status claims, or inaccurate summaries.

## 9. Use the smallest useful input

The safest and often best prompt uses only the context needed for the job.

Before pasting anything, ask:

- Does the model need this detail?
- Is this approved for the tool I am using?
- Can I anonymize it and still get useful output?
- Would I be comfortable explaining why this data was used?

If the answer is fuzzy, shrink the input.

## 10. End with movement

A TPM artifact should move the reader toward something: a decision, a follow-up, a risk acceptance, a tradeoff, or a next step.

If the output ends with everyone politely informed and no one clearer about what happens next, it is not done.
