# Google Workspace Prompt Pack

Google Workspace is where TPMs usually build the narrative: program docs, trackers, slides, meeting notes, and decision records.

Use these prompts when the source material is already sanitized and approved for the AI tool.

## Google Doc Program Charter

```text
Use the sanitized context below to draft a program charter.

Include:
1. Program name
2. Executive sponsor
3. DRI
4. Problem statement
5. Goals
6. Non-goals
7. Success metrics
8. Scope
9. Stakeholders
10. Milestones
11. Dependencies
12. Risks
13. Decision framework
14. Communication plan
15. Approval section

Write this so a new stakeholder can understand why the program exists, what is in scope, what is not, and what decision path we will use.

Context:
[paste sanitized context]
```

## Google Sheet Tracker Design

```text
Design a Google Sheets tracker for the program context below.

Include recommended columns for:
1. Workstream
2. Owner
3. Milestone
4. Status
5. Due date
6. Jira link or approved reference
7. Slack channel or approved reference
8. Dependency
9. Risk level
10. Next action
11. Last updated
12. Escalation needed

Also suggest useful filters, formulas, conditional formatting, and weekly review views. Keep the tracker simple enough that people will actually maintain it.

Context:
[paste sanitized context]
```

## Google Slides Executive Readout

```text
Turn the sanitized program context below into an executive readout outline for Google Slides.

Create:
1. Five slide titles
2. One key message per slide
3. Three supporting points per slide
4. Suggested chart or visual for each slide
5. Speaker notes for each slide

The deck should make status, risk, tradeoffs, and decisions clear. Do not bury the ask in the appendix.

Audience:
[paste audience]

Context:
[paste sanitized context]
```

## Google Doc Cleanup

```text
Review the sanitized Google Doc content below and improve its structure, clarity, and usefulness for the intended audience.

Return:
1. Cleaner outline
2. Sections that should be removed
3. Sections that need more detail
4. Ambiguous language to clarify
5. Suggested executive summary
6. Suggested decision section
7. Suggested risks section
8. Missing information to confirm before publishing

Do not rewrite weak facts into strong claims. If the document lacks evidence, call that out.

Document:
[paste sanitized doc]
```

## Review before publishing

- Confirm the document classification
- Remove comments or suggestions that should not be shared
- Validate dates, owners, and metrics
- Confirm customer, legal, and security language is approved
- Make sure the decision ask is easy to find
