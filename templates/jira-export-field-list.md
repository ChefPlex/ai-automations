# Jira Export Field List

Use these fields when exporting Jira data for TPM prompt workflows. Export the smallest useful set. More fields usually means more cleanup, not better output.

## Recommended fields

| Field | Why it matters |
|---|---|
| Issue key | Reference for validation |
| Issue type | Epic, story, task, bug, and risk if your site defines it |
| Summary | Work item description |
| Status | Current execution state |
| Assignee | Ownership |
| Reporter | Source context |
| Due date | Timing risk |
| Sprint or fix version | Milestone mapping |
| Parent | Work hierarchy and program grouping. On Jira Cloud this replaces Epic Link. |
| Epic link | Data Center only. Skip it on Cloud. |
| Labels | Program tags |
| Components | Service or team mapping |
| Priority | Relative urgency |
| Flagged | Blocker visibility. Jira's flag field; its one value is "Impediment". |
| Linked issues | Dependencies |
| Created date | Staleness check |
| Updated date | Staleness check |
| Acceptance criteria | Testability. A custom field, so the name varies by site. |
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
