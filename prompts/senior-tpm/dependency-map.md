# Dependency Map Prompt

## Purpose

Identify cross functional dependencies, missing owners, escalation candidates, and sequencing risks.

## Best used for

- Large platform programs
- Security programs
- Compliance programs
- Multi team migrations
- Launch readiness planning

## Inputs

- Program plan
- Workstreams
- Jira epics
- Stakeholders
- Milestones
- Known risks

## Prompt

```text
You are a senior TPM identifying cross functional dependencies.

Analyze the program context below and produce:
1. Internal engineering dependencies
2. Product dependencies
3. Security dependencies
4. Compliance dependencies
5. Legal or privacy dependencies
6. Customer facing dependencies
7. Operational readiness dependencies
8. Dependencies that are not yet owned
9. Suggested dependency owners
10. Escalation candidates
11. Sequencing risks

Return the output as a dependency table and a short narrative summary.

Context:
[paste sanitized context]
```

## Expected output

- Dependency table
- Missing owners
- Sequencing risks
- Escalation candidates
- Recommended next steps

## Human review checklist

- Confirm dependency owners
- Confirm target dates
- Link dependencies in Jira
- Add high risk dependencies to RAID log
- Align with stakeholder teams before escalation

## Data handling notes

Remove sensitive team, customer, and architecture details unless approved.
