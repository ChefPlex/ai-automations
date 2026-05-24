# Slack Thread Summary Prompt

## Purpose

Summarize long Slack threads into issue summaries, options, decisions, owners, and next actions.

## Best used for

- Blocker threads
- Cross functional alignment
- Decision threads
- Incident adjacent program conversations
- Engineering support threads

## Inputs

- Sanitized Slack thread
- Program context
- Current milestone
- Decision needed

## Prompt

```text
You are a TPM summarizing a long Slack thread.

Create:
1. A short summary of the discussion
2. The current issue
3. The proposed options
4. The apparent recommendation, if one exists
5. Open questions
6. People or roles who need to respond
7. Suggested next Slack message

Keep the tone collaborative and concise. Separate facts from assumptions. Do not treat opinions as confirmed decisions.

Slack thread:
[paste sanitized thread]
```

## Expected output

- Summary
- Issue
- Options
- Recommendation
- Open questions
- Responders needed
- Suggested Slack reply

## Human review checklist

- Confirm whether a decision was actually made
- Remove any sensitive content
- Confirm names or replace with roles
- Validate the suggested Slack reply before posting

## Data handling notes

Slack often contains informal comments, screenshots, and sensitive links. Sanitize before prompting.
