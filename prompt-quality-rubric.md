# Prompt Quality Rubric

Use this rubric to decide whether a TPM prompt is ready to share with another person. The question is not, "Did it produce something?" The question is, "Would I trust another TPM to use this safely and get a useful result?"

Score each category from 1 to 5.

| Category | 1 Weak | 3 Good | 5 Strong |
|---|---|---|---|
| Clarity | Vague ask | Clear task | Clear task, audience, and intended outcome |
| Context | Little context | Basic program context | Program, audience, source systems, risks, and decision context included |
| Output usefulness | Generic text | Usable draft | Clear artifact with owners, dates, risks, and next steps |
| Leadership fit | Too detailed or too casual | Mostly clear | Clear enough for a VP or director review |
| Risk visibility | Risk hidden or softened | Risk mentioned | Risk names impact, owner, mitigation, and escalation point |
| Tool fit | Ignores the source system | Mentions the source system | Fits the actual Jira, Slack, Salesforce, or Google Workspace workflow |
| Reuse | Only works once | Adaptable | Reusable across programs with clear placeholders |
| Safety | No safeguards | Some redaction guidance | Clear data handling and human review instructions |
| Decision quality | No decision ask | Some recommendation | Options, tradeoffs, recommendation, owner, and timing are clear |
| Time saved | Minimal | Helpful | Reduces manual work and improves the quality of the artifact |

## Score interpretation

| Score | Interpretation |
|---|---|
| 10 to 24 | Not ready |
| 25 to 34 | Usable with heavy review |
| 35 to 44 | Strong reusable prompt |
| 45 to 50 | Ready for broad use |

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

## Review questions before sharing a prompt

Ask these before adding a prompt to the repo:

- What real TPM problem does this solve?
- What source systems does it expect?
- What data should be removed first?
- Who is the audience for the output?
- What decision or next step should it support?
- What could the model get wrong?
- What must a human validate?

If those questions are hard to answer, the prompt is not ready yet. That is fine. Better to tighten it now than have someone find the gap in a leadership review.
