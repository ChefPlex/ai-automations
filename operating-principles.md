# Operating Principles

These principles define how TPMs should use AI in program execution.

## 1. AI is a clarity engine, not a decision maker

AI can help summarize, structure, rewrite, compare, and identify gaps. It should not make final decisions for program owners, engineering leaders, security leaders, legal teams, product leaders, or executives.

A TPM remains accountable for the quality and accuracy of the final artifact.

## 2. Signal over volume

The best TPM artifacts reduce noise. A good AI assisted output should make the following easier to find:

- Current status
- What changed
- What is blocked
- What is at risk
- Who owns the next action
- What decision is needed
- What happens if no action is taken

## 3. Facts, assumptions, and opinions must be separated

Every output should distinguish between:

- Confirmed facts
- Reasonable assumptions
- Open questions
- Recommendations

This is especially important for executive updates, customer escalations, compliance programs, launch readiness reviews, and incident adjacent work.

## 4. Do not polish away risk

AI can make writing sound more confident than the underlying facts support. TPMs should review every output to ensure risk, uncertainty, and blockers are not softened in a misleading way.

Preferred wording:

```text
The program is Yellow because two service teams have not committed migration dates, and the final validation environment is not available yet.
```

Avoid wording like:

```text
The program is progressing well with minor follow ups remaining.
```

## 5. Use AI to improve questions

Strong TPMs use AI to ask better questions, not just to write updates.

Examples:

- What dependency am I missing?
- What risk is hidden in this plan?
- What decision is actually needed?
- Who is the right decision maker?
- What data would change the recommendation?
- What is the cost of waiting?

## 6. Use AI outputs as drafts

Every output should be reviewed for:

- Accuracy
- Tone
- Dates
- Owners
- Risk language
- Customer impact
- Executive asks
- Security and privacy handling
- Alignment with source systems

## 7. The system of record still matters

AI summaries do not replace Jira, Salesforce, Google Docs, dashboards, or formal approval records.

After using AI, update the right system of record.

## 8. Good TPM automation improves team trust

A good AI assisted workflow should make teams feel more aligned, not more monitored. Use automation to remove manual burden, clarify ownership, and reduce ambiguity.

Do not use AI to surprise teams with public escalations, unreviewed status claims, or inaccurate summaries.
