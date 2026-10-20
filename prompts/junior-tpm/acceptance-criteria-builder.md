# Acceptance Criteria Builder Prompt

## Use this when

A Jira ticket is too vague for engineering, QA, security, support, or a program reviewer to know what done means.

## Where this fails

This prompt cannot know what the system is supposed to do beyond what the ticket says. When the ticket is vague, it will fill the gaps with reasonable-sounding criteria, and those quietly become requirements nobody asked for.

Have the engineering owner confirm every criterion before the ticket moves. Anything the model inferred belongs in the owner questions, not the acceptance criteria. A testable criterion can still test the wrong thing.

## Why it matters

Unclear acceptance criteria create rework. They also create polite disagreement at exactly the wrong time, usually near a milestone.

## Inputs to gather

- Existing Jira ticket
- Program goal
- Expected user or system behavior
- Validation method
- Known dependencies
- Out of scope items

## Prompt

```text
Rewrite the sanitized Jira ticket below so the acceptance criteria are clear, testable, and tied to the program goal.

Include:
1. Improved summary
2. Improved description
3. Acceptance criteria
4. Out of scope items
5. Dependencies
6. Validation method
7. Questions for the engineering owner

Do not add requirements that are not supported by the context. Mark missing information clearly.

Jira ticket:
[paste sanitized ticket]
```

## Expected output

- Improved ticket summary
- Improved description
- Acceptance criteria
- Out of scope list
- Dependencies
- Validation method
- Owner questions

## Human review checklist

- Acceptance criteria are testable
- Out of scope is explicit
- Dependencies are named
- Validation can be performed by a human or system
- No unsupported requirements were added


## Data handling notes

Remove internal links, customer names, security details, and proprietary implementation details unless approved.


## Done when

The ticket is ready when an engineer can start work and a reviewer can tell whether the work is complete.
