# Jira Export Field List

Use these fields when exporting Jira data for TPM prompt workflows.

## Recommended fields

| Field | Why it matters |
|---|---|
| Issue key | Reference for validation |
| Issue type | Epic, story, task, bug, risk |
| Summary | Work item description |
| Status | Current execution state |
| Assignee | Ownership |
| Reporter | Source context |
| Due date | Timing risk |
| Sprint or fix version | Milestone mapping |
| Epic link | Program grouping |
| Parent | Work hierarchy |
| Labels | Program tags |
| Components | Service or team mapping |
| Priority | Relative urgency |
| Blocked flag | Blocker visibility |
| Linked issues | Dependencies |
| Created date | Staleness check |
| Updated date | Staleness check |
| Acceptance criteria | Testability |
| Description | Context |

## Fields to review before prompting

Remove or sanitize:

- Customer identifiers
- Internal URLs
- Restricted security details
- Logs
- Secrets
- Architecture details
- Personal data
- Commercial details

## Useful derived fields

Add these in a spreadsheet before prompting:

- Days since last update
- Missing owner flag
- Missing due date flag
- Blocked without dependency flag
- Past due flag
- No acceptance criteria flag
- No linked dependency flag
