# Status Report Generator

A prompt-based workflow that reads raw inputs from a reporting period - meeting notes, Slack exports, RAID log updates, ticket summaries - and produces a complete draft status report.

The draft handles structure and assembly. You handle judgment.

---

## The Problem It Solves

The hard part of status reporting is not the writing. It is pulling a useful signal from a week of scattered notes, deciding what actually moved, figuring out what decisions are buried in meeting threads, and assembling it into a format that the right people will read.

This prompt does the first pass. It reads everything you give it, extracts what matters, structures it into a complete report, and flags the gaps you need to fill in before sending. You go from "staring at a blank page" to "editing a draft" - which is a fundamentally different and faster problem.

---

## Files

| File | What It Is |
|------|-----------|
| `status-report-generator-prompt.md` | The full prompt with instructions, section definitions, and usage guide |

---

## Folder Structure

Create this structure once per project. Add a dated inputs folder each reporting period.

```
~/status-reports/
  <project-name>/
    inputs/
      2026-06-09/
        meeting-notes.txt
        slack-brief.txt
        raid-log-updates.txt
        ticket-summary.txt
    outputs/
      2026-06-09-draft.md
      2026-06-09-draft.txt
```

For multiple projects, use one folder per project at the top level:

```
~/status-reports/
  platform-security/
  tls-modernization/
  compliance-2026/
```

**Google Drive:** Same structure works. Copy text from Drive documents into the prompt, or use a Claude conversation with Drive MCP enabled to read files directly.

---

## Quick Start

1. Create your inputs folder for the current period
2. Drop in whatever you have - rough meeting notes are fine, cleaned-up notes are better
3. Open Claude at claude.ai
4. Open `status-report-generator-prompt.md`
5. Copy the prompt from between the triple backtick fences
6. Paste your source material where it says `[PASTE YOUR INPUTS HERE]`
7. Fill in project name, your name, reporting period, date, audience, previous status
8. Send
9. Copy the output to `outputs/YYYY-MM-DD-draft.md`
10. Review, fill in NEEDS REVIEW items, verify the status call, remove Section 9, send

---

## What to Put in Inputs

**High value:**
- Meeting notes from the period (rough is fine)
- Action item lists with status updates
- RAID log changes - new risks, closed issues, escalating items
- Slack exports on key decisions or blockers
- Milestone or ticket status changes

**Also useful:**
- Last week's status report for context on what changed
- Email threads with significant decisions

**Not needed:**
- Full ticket backlogs
- Unrelated channel noise
- Meeting invites without notes

---

## Output Sections

The draft produces nine sections:

| Section | What It Contains |
|---------|----------------|
| 1. Overall Status | GREEN / YELLOW / RED with rationale |
| 2. Summary | 2-4 sentence executive summary |
| 3. Project Components | Budget, Schedule, Quality, Scope, Risks, Roadblocks - each with status and note |
| 4. Decisions Needed | Decision, owner, deadline, impact if delayed |
| 5. Key Accomplishments | 3-5 outcome-focused bullets with ticket/milestone references |
| 6. Upcoming Milestones | Target dates, owners, current status |
| 7. Risks and Issues | Typed, owned, with mitigation plans and change indicators |
| 8. Needs Review | Gaps the TPM needs to fill before sending |
| 9. Raw Source Notes | What was provided and what the key signals were (remove before sending) |

---

## Output Formats

**Markdown (.md):** Renders in GitHub, Notion, most tools. Copy to `outputs/` folder.

**Plain text (.txt):** Save the markdown as .txt. Tables render as ASCII - works anywhere.

**Word:** Paste markdown into Word. Tables paste cleanly.

**Excel template:** Section 3 (Project Components) maps directly to standard status report templates. Section 4 maps to Decisions. Sections 5-7 map to the work accomplished and risks tables.

**Slack canvas:** Paste markdown directly. Canvas renders tables.

---

## Integration With Slack Tools

The Slack Crawler in tpm-toolbox produces structured intelligence briefs. That output is excellent input for this prompt.

```
Slack Crawler (weekly)  →  inputs/YYYY-MM-DD/slack-brief.txt
Meeting notes           →  inputs/YYYY-MM-DD/meeting-notes.txt
RAID log changes        →  inputs/YYYY-MM-DD/raid-updates.txt
                                ↓
                    Status Report Generator
                                ↓
                    outputs/YYYY-MM-DD-draft.md
```

Running both tools in sequence typically reduces the Needs Review section to near zero because the Slack brief captures channel activity that meeting notes often miss.

---

## Maturity

| Tool | Status | Notes |
|------|--------|-------|
| Status Report Generator | Working | Requires Claude.ai or API access. Works best with structured inputs but handles rough notes. Always requires human review before sending. |

---

## What It Does Not Do

The prompt is explicit about this, but worth repeating:

- It does not decide whether the status is Green, Yellow, or Red. That judgment is yours.
- It does not know your org dynamics, what is politically sensitive, or what the sponsor needs to hear this week.
- It does not replace the review step. Read everything before sending.

A well-written draft that you review in five minutes is the point. Not an automated report that goes out without your eyes on it.

---

*Part of the [ai-automations](https://github.com/ChefPlex/ai-automations) repo. Built by [Eric White](https://github.com/ChefPlex).*
