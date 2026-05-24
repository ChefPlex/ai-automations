# Dependency Map Prompt

## Use this when

A program spans multiple teams and the TPM needs to know where handoffs, owners, and timing can break.

## Why it matters

Most program slips are not surprises. They usually live in unclear dependencies, soft commitments, and handoffs no one owns yet.

## Inputs to gather

- Program plan
- Workstreams
- Jira epics
- Team owners
- Target milestones
- Known blockers
- Compliance or security needs

## Prompt

```text
Review the sanitized program context below and build a dependency map.

Identify:
1. Internal engineering dependencies
2. Product dependencies
3. Security dependencies
4. Compliance dependencies
5. Legal or privacy dependencies
6. Customer-facing dependencies
7. Operational readiness dependencies
8. Dependencies without clear owners
9. Suggested owners
10. Escalation candidates

Return the output as a table with Dependency, Provider, Consumer, Needed By, Risk, Owner, and Next Step.

Context:
[paste sanitized context]
```

## Expected output

- Dependency table
- Unowned dependencies
- Critical path items
- Escalation candidates
- Questions to confirm

## Human review checklist

- Provider and consumer are both named
- Needed-by dates are present or marked missing
- Critical path items are clear
- Unowned dependencies are called out
- Next steps are specific


## Data handling notes

Remove internal links and sensitive technical, customer, or security details not needed for the mapping exercise.


## Done when

The map is ready when the TPM can tell which handoff is most likely to break the milestone.
