# Jira Export Field List

Use these fields when exporting Jira data for TPM prompt workflows. Export the smallest useful set. More fields usually means more cleanup, not better output.

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

Review and remove or sanitize:

- Customer names
- Internal links
- Sensitive technical details
- Security findings
- Incident details
- Personal data
- Commercial context
- Proprietary implementation details
- Comments that include confidential discussion

## TPM note

Jira is the system of record for work, but it is not always written for leadership. Use the export to ground the facts, then translate the work into outcomes, risks, and decisions.
