# Workflows

This directory contains end-to-end TPM workflows that combine prompts, source systems, review steps, and publishing guidance.

A prompt is useful. A workflow is better because it tells the TPM where the input comes from, how to clean it up, what to ask for, and where the final answer needs to land.

## Workflows included

- Weekly status workflow
- Customer escalation workflow
- Launch readiness workflow
- Compliance intake workflow
- Executive review workflow

## Workflow pattern

Each workflow follows the same basic structure:

1. Goal
2. Source systems
3. Inputs to gather
4. Safety checks
5. Prompt sequence
6. Where this fails
7. Human review checklist
8. Output artifacts
9. Systems to update

## Reminder

A workflow isn't complete until the right system of record is updated. If the update says the risk is mitigated but the RAID log still says open, the work isn't actually closed.
