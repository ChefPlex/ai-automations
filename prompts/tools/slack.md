# Slack Prompt Pack

Prompts for summarizing threads, aligning stakeholders, removing blockers, and deescalating conflict.

## Slack Message for Alignment

```text
Write a Slack message to align cross functional stakeholders.

The message should:
1. State the issue clearly
2. Summarize current understanding
3. Name the decision or action needed
4. Identify owners
5. Provide a deadline
6. Invite corrections
7. Keep the tone collaborative

Context:
[paste sanitized context]
```

## Slack Message for Blocker Removal

```text
Write a Slack message asking for help removing a blocker.

Tone should be respectful, clear, and direct.

Include:
1. What is blocked
2. Why it matters
3. Who is impacted
4. What help is needed
5. By when
6. What happens if it is not resolved
7. Suggested next step

Context:
[paste sanitized context]
```

## Slack Executive Update

```text
Write a brief Slack update for senior leadership.

Include:
1. Current health
2. Progress this week
3. Biggest risk
4. Decision needed, if any
5. Next milestone

Use fewer than 150 words. Do not overstate progress.

Context:
[paste sanitized context]
```

## Slack Conflict Deescalation

```text
You are helping a TPM respond to a tense Slack thread.

Write a message that:
1. Acknowledges the concern
2. Refocuses the group on the shared goal
3. Separates facts from assumptions
4. Proposes a concrete next step
5. Avoids blame
6. Creates a path to decision

Slack thread:
[paste sanitized thread]
```

## Data handling notes

Slack can include informal opinions, sensitive links, customer identifiers, and screenshots. Sanitize before prompting and validate the output before posting.
