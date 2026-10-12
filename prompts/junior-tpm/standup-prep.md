# Standup Prep Prompt

## Use this when

A program standup is coming up and the TPM needs to focus the conversation instead of walking ticket by ticket.

## Why it matters

A good standup is not a status recitation. It is a short operating checkpoint for blockers, dependencies, decisions, and next actions.

## Inputs to gather

- Current milestone
- Jira updates
- Known blockers
- Recent Slack threads
- Open risks
- Upcoming decision points

## Prompt

```text
Help me prepare for a program standup using the sanitized context below.

Create:
1. Top five topics to cover
2. Questions to ask each team or role
3. Blockers to validate
4. Dependencies to confirm
5. Decisions needed
6. Suggested agenda
7. Short opening statement for the TPM

Keep the agenda focused. Do not include topics that can be handled async.

Context:
[paste sanitized context]
```

## Expected output

- Focused agenda
- Team questions
- Blocker list
- Dependency checks
- Decision list
- Opening statement

## Where this fails

This prompt builds the agenda from the Jira updates and Slack threads you paste in. If those are a day old, the blockers it asks you to validate may already be cleared, and the one that showed up this morning will not be on the list. It will also produce five topics because it was asked for five, even on a quiet day.

Skim Jira and the team channels right before the standup. Drop topics that are already resolved, and keep the meeting short if there is less to cover.

## Human review checklist

- Agenda fits the meeting length
- Questions are assigned to the right team or role
- Async items are removed
- Blockers are specific
- Decision needs are clear


## Data handling notes

Remove names and internal links unless they are needed and approved for the tool.


## Done when

The standup is ready when the team can leave knowing what changed, what is blocked, and what each owner needs to do next.
