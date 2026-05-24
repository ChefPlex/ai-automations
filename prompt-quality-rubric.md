# Prompt Quality Rubric

Use this rubric to decide whether a TPM prompt is ready to share with another person.

The question is not, "Did it produce something?" The question is, "Would I trust another TPM to use this safely and get a useful result?"

Score each category from 1 to 5.

## Rubric

| Category | 1 - Weak | 3 - Good | 5 - Strong |
|---|---|---|---|
| Clarity | Vague ask | Clear task | Clear task, audience, and intended outcome |
| Context | Little context | Basic program context | Program, audience, source systems, risks, and decision context included |
| Output usefulness | Generic text | Usable draft | Clear artifact with owners, dates, risks, decisions, and next steps |
| Leadership fit | Too detailed, too casual, or too vague | Mostly clear | Clear enough for director or VP review |
| Risk visibility | Risk hidden or softened | Risk mentioned | Risk names impact, owner, mitigation, and escalation point |
| Tool fit | Ignores the source system | Mentions the source system | Fits the actual Jira, Slack, Salesforce, or Google Workspace workflow |
| Reuse | Only works once | Adaptable | Reusable across programs with clear placeholders |
| Safety | No safeguards | Some redaction guidance | Clear data handling and human review instructions |
| Decision quality | No decision ask | Some recommendation | Options, tradeoffs, recommendation, owner, and timing are clear |
| Failure handling | No failure mode named | Some caveats | Clear explanation of where the prompt breaks and what to verify |

## Score interpretation

| Score | Interpretation | What to do next |
|---|---|---|
| 10 to 24 | Not ready | Keep it private or rewrite it. It does not yet have enough structure or safety. |
| 25 to 34 | Usable with heavy review | Useful for the author, but not ready for broad reuse. Add examples and review checks. |
| 35 to 44 | Strong reusable prompt | Good candidate for the repo. Add or tighten failure modes before calling it done. |
| 45 to 50 | Ready for broad use | Ready to share, assuming the examples and safety notes are current. |

## Required sections for reusable prompts

A prompt file should include these sections before it is treated as reusable:

```text
What this does
When to use it
Input format
Prompt
Example input
Example output
Where this fails
Human review checklist
Data handling notes
```

If the example input or output lives in the `examples/` directory, link to it clearly.

## Weak prompt example

```text
Write a status update from this Jira data.
```

Why it is weak:

- No audience
- No program goal
- No definition of status
- No risk handling
- No decision ask
- No safety guidance
- No instruction to separate facts from assumptions

It may produce text, but the TPM still has to do most of the work.

## Better prompt example

```text
Use the sanitized Jira summary below to prepare a weekly program update for an engineering director.

Focus on what changed, what is blocked, what is at risk, and what decision is needed this week. Separate confirmed Jira status from assumptions. Do not make the program sound healthier than the data supports.

Context:
[paste sanitized context]
```

Why it is better:

- Names the audience
- Names the desired use
- Separates facts from assumptions
- Makes risk visible
- Asks for a decision-oriented output
- Tells the model not to overstate health

## Strong prompt pattern

```text
Use the sanitized context below to help me prepare [artifact] for [audience].

The goal is to make [decision, risk, status, tradeoff, or next step] clear.

Please produce:
1. A short summary
2. The key facts
3. Any assumptions
4. Risks or blockers
5. Options or tradeoffs, if relevant
6. Recommended next action
7. Missing information I should confirm before sending

Do not invent facts. Do not overstate progress or customer impact. Use clear, direct language.

Context:
[paste sanitized context]
```

## Human review checklist

Before sharing a prompt output, check:

- Are the dates real?
- Are the owners real?
- Are Jira statuses current?
- Are assumptions labeled?
- Are risks visible without being exaggerated?
- Is the decision ask clear?
- Is the output appropriate for the audience?
- Does the output create any accidental customer, legal, security, or roadmap commitment?
- Is any sensitive data still present?

## Review questions before adding a prompt

Ask these before adding a prompt to the repo:

- What real TPM problem does this solve?
- What source systems does it expect?
- What data should be removed first?
- Who is the audience for the output?
- What decision or next step should it support?
- What could the model get wrong?
- What must a human validate?
- Where does this prompt fail?

If those questions are hard to answer, the prompt is not ready yet. That is fine. Better to tighten it now than have someone find the gap in a leadership review.

## Stop signs

Do not publish or reuse a prompt when it:

- Invents owners, dates, ticket IDs, metrics, or decisions
- Turns uncertainty into confidence
- Hides risk behind pleasant language
- Requires sensitive raw data when a sanitized summary would work
- Produces an artifact that sounds better but does not help anyone act
- Has no human review checklist
- Has no failure mode

A prompt that only makes something sound nicer is not ready. Useful is the bar.
