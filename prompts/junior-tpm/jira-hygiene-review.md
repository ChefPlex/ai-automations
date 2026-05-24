# Jira Hygiene Review Prompt

## Use this when

A Jira epic or sprint looks noisy, stale, or hard to trust, and the TPM needs a cleanup plan.

## Why it matters

Jira does not have to be perfect, but it does need to be useful. If ownership, dates, acceptance criteria, and dependencies are unclear, program status becomes guesswork.

## Inputs to gather

- Jira issue export or summary
- Epic goal
- Target milestone
- Known dependencies
- Current sprint or release context

## Prompt

```text
Review the sanitized Jira issues below for program hygiene.

Identify:
1. Tickets missing owners
2. Tickets missing due dates
3. Tickets with unclear acceptance criteria
4. Tickets that appear stale
5. Tickets that are blocked but not marked blocked
6. Tickets that may belong under a different epic
7. Tickets that need dependency links
8. Suggested cleanup actions

Return a table with Issue, Problem, Why It Matters, Recommended Fix, and Owner Question.

Jira data:
[paste sanitized Jira export or ticket summaries]
```

## Expected output

- Jira cleanup table
- Top hygiene risks
- Questions for owners
- Recommended next cleanup step

## Human review checklist

- No customer names or sensitive details remain
- Each recommendation is specific
- Blocked work is called out plainly
- Stale tickets are based on update dates or evidence
- Recommended changes can be validated in Jira


## Data handling notes

Jira exports may include internal links, customer references, security details, and comments. Remove anything not needed for the review.


## Done when

The review is ready when the TPM can run a 15 minute cleanup with owners instead of debating what the tickets mean.
