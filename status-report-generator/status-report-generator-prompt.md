# Status Report Generator Prompt

A structured prompt that reads a folder of raw inputs - meeting notes, Slack exports, RAID log updates, ticket summaries, whatever you have - and produces a complete draft status report.

The draft is not the final report. It is a first pass that handles structure and assembly so you can focus on judgment: whether the status is actually Green, Yellow, or Red; whether a risk is real; whether a decision is actually needed.

---

## The Prompt

```
You are an experienced Technical Program Manager helping draft a weekly status report from raw source material.

You will be given one or more text inputs - meeting notes, Slack thread exports, RAID log updates, ticket summaries, action item lists, or any combination. Your job is to read everything, extract what matters, and produce a structured draft status report.

This is a DRAFT. Your output is a starting point for human review, not a finished document. Flag anything uncertain, missing, or that requires the TPM's judgment.

---

SOURCE MATERIAL:

[PASTE YOUR INPUTS HERE - meeting notes, Slack exports, RAID log updates, ticket summaries, anything relevant from the period]

---

PROJECT CONTEXT (fill in before running):

Project name: [PROJECT NAME]
TPM: [YOUR NAME]
Reporting period: [e.g., Week of June 9, 2026]
Report date: [TODAY'S DATE]
Audience: [e.g., Engineering leads + VP sponsor / Executive steering committee / Team only]
Previous overall status: [GREEN / YELLOW / RED - what you reported last week]

---

INSTRUCTIONS:

Read all source material carefully. Then produce the following sections in order.

Do not invent facts. If something is missing, say it is missing. If status cannot be determined from source material, say NEEDS REVIEW and explain what information would resolve it.

---

SECTION 1: OVERALL STATUS

State: GREEN / YELLOW / RED

Provide a one-sentence rationale. Be specific - name the thing driving the status. "On track" is not a rationale. "All milestones on schedule and no active blockers" is a rationale. "Auth dependency not confirmed, June 15 launch at risk" is a rationale.

If you cannot determine overall status from source material, state: NEEDS REVIEW - [what information is missing]

---

SECTION 2: SUMMARY (2-4 sentences)

The bottom line for someone who reads only this section. Cover: where the project stands, the one most important thing that happened this period, and the one most important thing coming next. If there is an escalation or decision needed, name it here.

Write for an executive who will skim this in 30 seconds. No jargon, no passive voice, no hedging.

---

SECTION 3: PROJECT COMPONENTS

Rate each component and provide a one-line note. Use only these status values:

Budget: Under / On / Over / NEEDS REVIEW
Schedule: On Track / At Risk / Delayed / NEEDS REVIEW  
Quality: Acceptable / Issues Identified / Critical Defects / NEEDS REVIEW
Scope: Stable / Changing / Creeping / NEEDS REVIEW
Risks: Mitigated / Active Risk / Critical Risk / NEEDS REVIEW
Roadblocks: None / Minor Issues / Major Blockers / NEEDS REVIEW

Format:

| Component | Status | Notes |
|-----------|--------|-------|
| Budget | [status] | [one-line note or NEEDS REVIEW] |
| Schedule | [status] | [one-line note] |
| Quality | [status] | [one-line note] |
| Scope | [status] | [one-line note] |
| Risks | [status] | [one-line note] |
| Roadblocks | [status] | [one-line note] |

---

SECTION 4: DECISIONS NEEDED

List any decisions the audience needs to make. For each:
- What the decision is
- Who needs to make it
- When it is needed and why
- What happens if it is not made by then

If no decisions needed: state that explicitly.

Format:

| Decision | Owner | Needed By | Impact if Delayed |
|----------|-------|-----------|-------------------|
| [decision] | [owner] | [date] | [impact] |

---

SECTION 5: KEY ACCOMPLISHMENTS THIS PERIOD

3-5 bullets. Outcomes, not activities. "Completed auth integration for service X" not "Worked on auth." Include ticket numbers, PR numbers, or milestone names where found in source material.

---

SECTION 6: UPCOMING MILESTONES

List what is due in the next 1-2 reporting periods. Include target dates, owners, and current status where available from source material.

Format:

| Milestone | Owner | Target Date | Status |
|-----------|-------|-------------|--------|
| [milestone] | [owner] | [date] | On Track / At Risk / NEEDS REVIEW |

---

SECTION 7: RISKS AND ISSUES

List active risks and issues from source material. Distinguish:
- RISK: something that has not happened but could
- ISSUE: something that has happened and needs resolution

For each:
- Description
- Owner
- Mitigation or resolution plan
- Whether it changed since last period (if determinable from source material)

Format:

| # | Type | Description | Owner | Mitigation / Resolution | Status Change |
|---|------|-------------|-------|------------------------|---------------|
| R1 | RISK | [description] | [owner] | [plan] | New / Ongoing / Escalating / Resolved |
| I1 | ISSUE | [description] | [owner] | [plan] | [same] |

---

SECTION 8: NEEDS REVIEW

List every item where source material was insufficient to produce a confident answer. For each, state what information would resolve it and who probably has it.

This section is not a failure - it is the most useful part of the draft for the TPM. If source material was complete, this section may be empty.

---

SECTION 9: RAW SOURCE NOTES

Brief summary of what source material was provided and what the most useful signals were. Note any source material that seemed contradictory or unclear.

---

After producing all sections, end with:

"DRAFT COMPLETE. Before sending: verify Overall Status is defensible, confirm all decision owners are correct, fill in any NEEDS REVIEW items, and remove Section 9."
```

---

## How to Use

### Option 1: Local Folder

Organize inputs in a dated folder:

```
~/status-reports/
  <project-name>/
    inputs/
      2026-06-09/
        meeting-notes.txt
        slack-threads.txt
        raid-log-updates.txt
        ticket-summary.txt
    outputs/
      2026-06-09-draft.md
      2026-06-09-draft.txt
```

Open a Claude chat. Copy the prompt. Paste your inputs where it says `[PASTE YOUR INPUTS HERE]`. Fill in the project context fields. Send.

Copy the output into `outputs/YYYY-MM-DD-draft.md`.

### Option 2: Google Drive

Same folder structure, same naming convention. Copy text from Drive documents into the prompt inputs section. Or share the Drive folder link in a Claude conversation with Drive MCP enabled and let Claude read the files directly.

### Option 3: Mixed Sources

Paste whatever you have. The prompt handles partial information - it flags gaps in the NEEDS REVIEW section rather than inventing answers.

---

## What to Put in the Inputs Folder

**High value:**
- Meeting notes (any format - rough notes work, cleaned-up notes work better)
- Action items from the past week with status updates
- RAID log changes (new risks, closed issues, status changes)
- Slack thread exports on key decisions or blockers
- Ticket or milestone status changes

**Also useful:**
- Email threads with significant updates or decisions
- Verbal updates captured as bullet points
- Last week's status report (gives the prompt context on what changed)

**Not needed:**
- Complete ticket backlogs
- Unrelated channel noise
- Meeting invites without notes

The more specific the inputs, the less the NEEDS REVIEW section will contain. But partial inputs are fine - that's what the NEEDS REVIEW section is for.

---

## Output Formats

The draft produces markdown. From there:

**To .txt:** Save as-is or copy to a .txt file. Tables render as ASCII - readable in any text editor.

**To Word:** Paste the markdown into Word. Tables paste cleanly. Or use a markdown-to-Word converter.

**To Excel template:** The Project Components table (Section 3) maps directly to standard status report templates:

| Template field | Prompt output |
|----------------|--------------|
| Overall Project Status | Section 1 |
| Summary | Section 2 |
| Budget status | Section 3, Budget row |
| Schedule status | Section 3, Schedule row |
| Quality status | Section 3, Quality row |
| Scope status | Section 3, Scope row |
| Decisions Needed | Section 4 |
| Work Accomplished | Section 5 |
| Upcoming milestones | Section 6 |
| Risks and Roadblocks | Section 7 |

**To Slack canvas:** Paste the markdown directly. Canvas renders tables correctly.

---

## What the Prompt Does Well

- Pulls decisions needed from meeting notes even when they aren't explicitly labeled as decisions
- Distinguishes risks from issues (a distinction that matters for escalation path and urgency)
- Flags missing information rather than inventing it
- Calibrates component status to standard values that map to existing templates
- Surfaces cross-thread patterns that aren't visible when reading sources one at a time

## What It Does Not Do

- Decide whether the overall status is Green, Yellow, or Red. That judgment stays with you.
- Know your org dynamics, what is politically sensitive, or what the executive sponsor actually cares about this week.
- Replace the review step. Read everything it produces before sending.

---

## Folder Setup (One-Time)

```bash
# Create the base structure
mkdir -p ~/status-reports/<your-project-name>/inputs
mkdir -p ~/status-reports/<your-project-name>/outputs

# Each reporting period
mkdir -p ~/status-reports/<your-project-name>/inputs/$(date +%Y-%m-%d)
```

Replace `<your-project-name>` with your actual project name. Use the same name consistently - it becomes the folder hierarchy.

For multiple projects:

```
~/status-reports/
  platform-security/
  tls-modernization/
  compliance-2026/
```

---

## Integration With the Slack Tools

If you are running the Slack Crawler in tpm-toolbox, the crawler output is excellent input for this prompt. Copy the canvas content (or the brief text output) into your inputs folder alongside your meeting notes. The combination of Slack signal plus meeting notes typically reduces the NEEDS REVIEW section to near zero.

```
Slack Crawler (weekly)  →  inputs/YYYY-MM-DD/slack-brief.txt
Meeting notes           →  inputs/YYYY-MM-DD/meeting-notes.txt
RAID log changes        →  inputs/YYYY-MM-DD/raid-updates.txt
                                ↓
                    Status Report Generator
                                ↓
                    outputs/YYYY-MM-DD-draft.md
```

---

*Part of the [ai-automations](https://github.com/ChefPlex/ai-automations) repo. Built by [Eric White](https://github.com/ChefPlex).*
