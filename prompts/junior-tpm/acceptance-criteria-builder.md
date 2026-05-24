# Acceptance Criteria Builder Prompt

## Purpose

Improve Jira ticket quality by making acceptance criteria clear, testable, and aligned to program goals.

## Best used for

- Jira story cleanup
- Sprint planning
- Milestone planning
- Engineering handoff
- QA validation planning

## Inputs

- Jira ticket draft
- Program goal
- Expected behavior
- Validation method
- Dependencies

## Prompt

```text
You are helping a junior TPM improve Jira ticket quality.

Rewrite the Jira ticket below so that the acceptance criteria are clear, testable, and aligned to the program goal.

Include:
1. Improved summary
2. Improved description
3. Acceptance criteria
4. Out of scope items
5. Dependencies
6. Validation method
7. Questions for the engineering owner

Do not add technical requirements that are not supported by the context. Mark uncertain items as questions.

Jira ticket:
[paste sanitized ticket]
```

## Expected output

- Improved Jira summary
- Improved description
- Acceptance criteria
- Out of scope
- Dependencies
- Validation method
- Engineering questions

## Human review checklist

- Engineering owner approves technical details
- Acceptance criteria are testable
- Scope is clear
- Dependencies are linked in Jira

## Data handling notes

Remove internal links, customer identifiers, and sensitive implementation details before prompting.
