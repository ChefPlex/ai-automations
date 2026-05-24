# Executive Program Update Prompt

## Use this when

Program inputs are scattered across Jira, Slack, Salesforce, Google Docs, and meeting notes, and leadership needs the real picture without the noise.

## Why it matters

An executive update should make the decision path clear. It should not list every task. It should explain what changed, why it matters, what is at risk, and what help is needed.

## Inputs to gather

- Program objective
- Current milestone
- Jira epic or sprint summary
- Slack blocker threads
- Salesforce customer signals, if approved
- RAID log updates
- Decisions needed
- Target audience

## Prompt

```text
Help me prepare an executive program update using the sanitized context below.

Create:

1. Overall status as Green, Yellow, or Red
2. One paragraph executive summary
3. What changed since the last update
4. Progress against milestones
5. Customer or business impact
6. Top risks with owner, mitigation, and escalation point
7. Blockers requiring leadership help
8. Decisions needed this week
9. Recommended next action
10. Missing information I should confirm before sending

Keep the language direct and calm. Do not make the program sound healthier than the evidence supports. Separate facts from assumptions.

Context:

[paste sanitized context]
```

## Expected output

- Executive summary
- Status with rationale
- Key updates
- Milestone progress
- Risks and blockers
- Decisions needed
- Recommended next action
- Missing information

## Example

See:

- [Executive update input context](../../examples/executive-update-input-context.md)
- [Executive update output](../../examples/executive-update-output.md)

These examples show the intended standard: concise enough for leadership, but still honest about risk, blockers, missing information, and the decision needed.

## Human review checklist

- Status matches the facts
- Customer impact is approved and not overstated
- Security details are sanitized
- Dates and owners are accurate
- The executive ask is obvious
- Risks are not softened
- Missing information is called out instead of papered over

## Data handling notes

Be careful with customer signals, security risks, legal commitments, and revenue impact. Use only approved and sanitized context.

Do not paste customer names, contract details, vulnerability details, unreleased roadmap commitments, or internal links unless the AI tool and audience are approved for that data.

## Where this fails

This prompt works best when the source material contains real signal: dates, owners, milestones, risks, blockers, and decisions needed.

It works poorly when the input is mostly vague status language, stale Jira data, or Slack opinions that have not been confirmed. In those cases, the output may sound polished while still being wrong.

Watch for the dangerous version of a bad output: a clean executive update that makes the program sound more certain than the evidence supports.

## Done when

The update is ready when a VP can read it quickly and know whether to decide, escalate, accept risk, or stay the course.
