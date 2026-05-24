# Prompt Quality Rubric

Use this rubric to evaluate whether a TPM prompt is ready for use.

Score each category from 1 to 5.

| Category | 1 Weak | 3 Good | 5 Excellent |
|---|---|---|---|
| Clarity | Vague ask | Clear task | Clear task, audience, and outcome |
| Context | Little context | Basic program context | Full program, stakeholder, tool, and risk context |
| Output usefulness | Generic text | Usable draft | Actionable artifact with owners, dates, and decisions |
| Executive readiness | Too detailed or casual | Mostly clear | Concise, decision oriented, leadership ready |
| Risk visibility | Hides risks | Mentions risks | Names risks, impact, mitigation, owner, and escalation threshold |
| Tool fit | Ignores source system | References source system | Optimized for Jira, Slack, Salesforce, or Google Workspace workflow |
| Reusability | One off | Adaptable | Reusable across programs with clear placeholders |
| Safety | No safeguards | Some redaction | Strong data handling and human review instructions |
| Decision quality | No decision ask | Some recommendation | Clear options, tradeoffs, recommendation, and decision owner |
| Time saved | Minimal | Helpful | Reduces manual work while improving quality |

## Score interpretation

| Score | Interpretation |
|---|---|
| 10 to 24 | Not ready |
| 25 to 34 | Usable with heavy review |
| 35 to 44 | Strong reusable prompt |
| 45 to 50 | Director level prompt |

## Weak prompt example

```text
Write a status update for this project.
```

Why it is weak:

- No audience
- No source context
- No output format
- No risk or decision guidance
- No data handling guardrails

## Good prompt example

```text
Create a weekly status update from the Jira and Slack context below. Include status, progress, risks, blockers, decisions needed, and next steps.

Context:
[paste context]
```

Why it is good:

- Clear artifact
- Clear source systems
- Basic structure
- Usable output

## Excellent prompt example

```text
You are acting as a senior TPM preparing a VP level weekly update for a platform security program.

Use the sanitized Jira, Slack, Salesforce, and meeting note context below.

Create an executive ready update with:
1. Overall program health as Green, Yellow, or Red
2. What changed since the last update
3. Progress against milestones
4. Customer or business impact
5. Top risks with owner and mitigation
6. Blockers requiring leadership help
7. Decisions needed this week
8. Recommended next action

Separate facts from assumptions. Do not overstate progress. Identify missing information.

Context:
[paste sanitized context]
```

Why it is excellent:

- Defines role and audience
- Names source systems
- Requires risk and decision clarity
- Requires safe reasoning boundaries
- Produces an actionable artifact
