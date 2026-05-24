# Meeting Notes to Action Items Prompt

## Use this when

A meeting produced useful discussion, but the notes are messy and the team needs decisions, owners, and next steps pulled out cleanly.

## Why it matters

Meetings usually fail in the handoff. The value is not the notes. The value is knowing what was decided, what is still open, and who is doing what by when.

## Inputs to gather

- Meeting notes
- Meeting purpose
- Attendees or roles
- Program context
- Known deadlines
- Any decisions already confirmed

## Prompt

```text
Use the sanitized meeting notes below and turn them into a clean follow-up.

Extract:
1. Decisions made
2. Open questions
3. Action items
4. Owners
5. Due dates
6. Risks raised
7. Follow-up meetings or reviews needed
8. Items that need confirmation because the notes are unclear

Write the action items in a format I can paste into Slack or Jira. Do not invent owners or dates. If they are missing, mark them as missing.

Meeting notes:
[paste sanitized notes]
```

## Expected output

- Decision list
- Open questions
- Action item table
- Risks raised
- Follow-up needed
- Missing information

## Human review checklist

- Every action has an owner or is marked owner needed
- Every date is confirmed or marked date needed
- Decisions are not confused with discussion points
- Risks are not softened
- No sensitive information remains


## Data handling notes

Remove names, customer references, internal links, and restricted technical details unless they are approved for the AI tool.


## Done when

The follow-up is ready when someone who missed the meeting can understand what happened and what they owe.
