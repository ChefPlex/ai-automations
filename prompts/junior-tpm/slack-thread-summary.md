# Slack Thread Summary Prompt

## Use this when

A Slack thread has useful signal buried in discussion, side comments, and partial answers.

## Why it matters

Slack is where blockers surface early, but it is not always where decisions are cleanly recorded. This prompt helps pull out the facts without treating every comment as truth.

## Inputs to gather

- Sanitized Slack thread or summary
- Program context
- Known decision needed
- Relevant Jira or doc reference, if safe

## Prompt

```text
Summarize the sanitized Slack thread below for TPM follow-up.

Create:
1. Short summary of the discussion
2. Current issue
3. Proposed options
4. Apparent recommendation, if one is supported by the thread
5. Open questions
6. People or roles who need to respond
7. Suggested next Slack message

Separate confirmed facts from assumptions. Do not treat opinions as decisions.

Slack thread:
[paste sanitized thread or summary]
```

## Expected output

- Discussion summary
- Current issue
- Options
- Recommendation if supported
- Open questions
- Suggested reply

## Human review checklist

- Names and sensitive details are removed unless approved
- No opinion is presented as fact
- Decision status is clear
- Suggested reply is respectful and direct
- Next step is obvious


## Data handling notes

Slack may contain customer names, screenshots, personal data, internal links, incident details, or pasted code. Summarize first when possible.


## Done when

The summary is ready when it can be pasted into the program channel and reduce confusion instead of restarting the whole thread.
