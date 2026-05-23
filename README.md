# ai-automations

AI-powered scripts, prompts, and workflows for TPM productivity and program management. Built from actual daily use - things that save real time on the job, not proof-of-concept demos.

The tools here are not about replacing judgment. They are about removing the mechanical work so there is more time for the work that actually requires it.

---

## What Is Here

Nothing yet. This repo is the starting point.

The first tools will come from what I use regularly and can document well enough to be useful to someone else. That bar is higher than it sounds. A prompt that works for me in my context is not automatically a tool. A tool is something documented, reproducible, and general enough to be worth sharing.

---

## What Is Coming

### Status Reporting

**Status Report Generator** - Feed it a week's worth of meeting notes, ticket updates, and RAID log changes. Get a structured status report in the format that matches the Communications Plan template in tpm-templates. The hard part of status reporting is not the writing - it is pulling the signal from a week of noise. This handles the first pass.

**RAID Log Summarizer** - Takes a populated RAID log and generates an executive-level risk summary: what is hot, what closed, what needs a decision. Useful for the steering committee prep section of the week.

### Meeting Support

**Meeting Notes Processor** - Takes raw meeting notes (rough, stream of consciousness, whatever you actually typed) and extracts decisions, action items, and open questions in the format from the meeting notes template in tpm-templates. One prompt, structured output.

**Pre-Meeting Brief Generator** - Given a meeting agenda and participant list, generates a one-page brief: what each participant likely cares about, what decisions are needed, and what the blockers are likely to be. Useful before steering committees and exec reviews.

### Program Health

**Program Health Check** - Given a charter, a RAID log, and a status history, generates a structured assessment of where the program stands relative to where it should be at this phase of the lifecycle. Surfaces things that are easy to miss when you are close to the work.

**Escalation Draft** - Takes a problem description and generates a structured escalation: what is happening, what the impact is, what has been tried, what decision or action is needed from the escalation target. Hard to write under pressure. Easier with a starting point.

### Compliance and Security

**Compliance Intake Triage** - Given a new regulatory requirement or audit finding, generates an initial analysis: which systems and programs are likely in scope, what evidence will probably be needed, and what the remediation timeline might look like. First cut, not a substitute for GRC review.

**Evidence Request Translator** - Takes an auditor's evidence request (which is often written in auditor language) and translates it into plain language: what they are actually asking for, what a complete response looks like, and who in the organization likely owns it.

---

## Design Principles

**Output you can use, not output you have to rewrite.** The prompts here are tuned for the specific formats and contexts in the other ChefPlex repos. They produce things that slot into existing workflows.

**Transparent about what AI is good at and what it is not.** AI is good at structure, first drafts, and pattern recognition. It is not good at knowing your specific situation, your org dynamics, or what the executive in the room actually cares about. These tools handle the structural work. The judgment stays with you.

**Documented well enough to be adapted.** Every tool here will include the prompt, the expected input format, the expected output format, and notes on where it tends to go wrong. If you need to adapt it to your context, you should be able to do that without reverse-engineering it.

**Lightweight.** No frameworks, no dependencies, no setup. A prompt you can run in Claude, ChatGPT, or whatever model you are using. If something here requires infrastructure, it will be documented clearly and the infrastructure will be minimal.

---

## How This Fits With the Other Repos

These tools are designed to work alongside the content in the other ChefPlex repos:

- **tpm-templates** - the output formats these tools produce match the templates there
- **program-reporting-frameworks** - the status and steering committee tools feed directly into those frameworks
- **tpm-toolbox** - scripts here may eventually include toolbox-compatible automation

The repos are separate because templates, tools, and automation serve different purposes. They are designed to work together.

---

## Contributing

If you have a prompt, script, or workflow that saves real time on TPM work and can be documented well enough to be useful to someone else, open a PR or file an issue. The bar is: it has to work, it has to be documented, and it has to be general enough to apply outside one specific organization.

---

*Built from experience running platform security, infrastructure, and compliance programs at enterprise scale. Maintained by [Eric White](https://www.linkedin.com/in/edwhite) | [ChefPlex](https://github.com/ChefPlex)*
