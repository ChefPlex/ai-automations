# Artifact Critique Prompt

## Use this when

A TPM artifact is close, but it needs a director-level review before it goes to leadership or a broad audience.

## Why it matters

A good review does not just clean up writing. It tests whether the artifact has the right context, risk, ownership, decision quality, and audience fit.

## Inputs to gather

- Artifact draft
- Audience
- Program context
- Decision needed
- Known risks
- Any sensitive data constraints

## Prompt

```text
Act as a director-level Technical Program Manager reviewing the artifact below.

Evaluate it for:

1. Strategic clarity
2. Customer or business impact
3. Technical depth
4. Execution realism
5. Risk visibility
6. Dependency management
7. Ownership clarity
8. Decision quality
9. Audience fit
10. Missing information

Then provide:

1. Concise critique
2. Stronger rewritten version
3. Questions I should answer before sending
4. Risks I may be underestimating
5. Recommended next action

Do not make the artifact sound more positive than the facts support.

Artifact:

[paste sanitized artifact]
```

## Expected output

- Critique
- Rewritten artifact
- Questions to answer
- Underestimated risks
- Recommended next action

## Example

See:

- [Artifact critique input](../../examples/artifact-critique-input.md)
- [Artifact critique output](../../examples/artifact-critique-output.md)

These examples show the intended behavior: make the artifact sharper, but do not hide the risk just because the rewrite sounds better.

## Human review checklist

- The rewrite keeps the facts intact
- Risk language is not softened
- Decision ask is clearer
- Audience fit is improved
- Missing information is explicit
- The critique says what is actually wrong, not just what could be nicer

## Data handling notes

Remove sensitive customer, security, legal, commercial, and internal details before prompting.

If the artifact contains executive names, customer details, legal commitments, vulnerability details, or internal incident facts, sanitize or summarize those details before using an AI tool.

## Where this fails

This prompt can make weak content sound finished. That is useful for style, but dangerous for judgment.

The failure mode is a polished artifact that still has no owner, no date, no real decision ask, or no honest risk statement. Do not accept the rewrite just because it reads better. Check that it is truer and more useful.

## Done when

The artifact is ready when the reader can understand the situation, the risk, and the ask without needing a pre-brief.
