# Four-Lens Codebase Audit Workflow

## Goal

Get a ranked, defensible list of the defects in a codebase in days, where a manual review of the same scope takes weeks. AI reviews the code through four separate lenses, and a person reconciles, verifies and ranks what comes back.

A single "review this codebase" prompt produces a summary that reads like a review. One pass mixes architecture opinions, security findings and test gaps, and whichever category is loudest crowds out the rest. Splitting the work into lenses forces each pass to look hard at one thing.

In terms of the [execution tiers](../frameworks/ai-execution-tiers.md), the AI produces the findings and a person owns the verdict (tier 3). No finding goes to an engineering backlog until a person has read the code it points at.

When this was run on a production codebase, the top-ranked findings were later confirmed by the external audit that followed. That check is step 7 of the method.

## The four lenses

| Lens | The question it asks | Typical findings |
|:---|:---|:---|
| **Architecture** | Does the structure hold up as the system grows? Boundaries, coupling, data flow, single points of failure. | The same business rule in three layers. A component that knows too much about its neighbours. |
| **Security** | What can an attacker, or a careless user, do? Authentication, authorization, input handling, secrets, data exposure, dependencies. | A permission check in the interface but not on the server. A credential in a config file. |
| **Backend** | Does the server-side code do what it claims under load and under failure? Error handling, transactions, concurrency, data integrity. | Exceptions caught and dropped. A write that can half-complete. |
| **QA** (quality assurance) | What is tested, what is not, and does the suite prove the requirements? | Requirements with no test. Tests that run but assert nothing. |

## Inputs to gather

- The code at a pinned commit. Record the hash; every lens reviews the same code.
- The requirements or product specification, if one exists. The QA lens needs it.
- An architecture diagram, or the closest thing to one
- The known-issues list, so the audit does not spend its time rediscovering them
- Scope: which repositories and services are in, and which are out

## Safety checks

- Use an AI tool approved for source code, and read its data-handling terms. Code carries secrets, and test fixtures sometimes carry real customer data.
- Scan for secrets before the first lens runs. Rotate anything found; do not just delete it.
- No production data in prompts.
- The findings are sensitive in their own right. A ranked list of security weaknesses belongs somewhere with controlled access, not in a shared channel.

## Prompt sequence

1. **Pin the commit.** Every lens reviews the same snapshot.
2. **Run each lens in its own session**, with no access to the other lenses' output. A lens that has read the security findings starts agreeing with them.
3. **Collect the findings in one format**, using the lens prompt below.
4. **Reconcile.** Merge duplicates. Pay attention where two lenses reached the same root cause from different sides; those are usually the findings that matter most.
5. **Verify.** A person reads each finding against the code and labels it confirmed, plausible, or rejected. Plausible means the code alone could not prove it either way.
6. **Rank** the confirmed and plausible findings by impact, likelihood and rough effort, with one sentence of reasoning each.
7. **Check against an independent review** when one exists: an external audit, a penetration test, or a reviewer who did not set up the lenses. Record what both found, and what only one of them found.

### Lens prompt

```text
Review this codebase through ONE lens only: [architecture | security | backend | QA].

Codebase at commit: [hash]
Scope: [paths in scope]

For each finding return:
- ID
- Title
- Location (file and line, or component)
- What is wrong, in two sentences
- Evidence: the code or configuration that shows it
- Impact if it is left alone
- Confidence (high, medium or low) and what would raise it

Do not report style preferences. Do not report anything you cannot point to in
the code. List the areas you checked and found nothing. If you see something
severe outside your lens, put it at the end under "Outside my lens".
```

## Final prompt

```text
Below are findings from four separate reviews of the same codebase at commit
[hash]: architecture, security, backend and QA.

1. Group findings that share a root cause, even where the lenses describe
   them differently. Name the lenses that raised each group.
2. Flag any finding that one lens contradicts.
3. Propose a priority order using impact, likelihood and rough effort to fix.
   Give one sentence of reasoning per item.
4. List what each lens said it checked and found nothing in.

Do not add new findings. Do not drop a finding without saying why. Every item
still needs a person to confirm it against the code before anyone acts on it.

Findings:
[paste the four lens outputs]
```

## Where this fails

**One model with four prompts is not four reviewers.** Lenses run on the same model share its blind spots. If all four miss a class of defect, their agreement means nothing. Step 7 exists for this reason. If you can, run at least one lens on a different model, or have a person do it.

**A long list looks thorough.** What matters is whether the top of the ranking holds up when someone independent looks at it.

**Plausible becomes confirmed by repetition.** Keep the label until someone proves it one way or the other.

**On a small team, nobody is independent.** The person who wrote the lens prompts is often the person who reconciles and ranks the output. Say so in the summary, and lean harder on step 7.

The audit finds what is visible in the code. It does not find what is missing from the requirements, what is misconfigured in production, or what is wrong in the process around the code. It does not replace a penetration test or a compliance audit. Run it before one.

## Human review checklist

- Each lens ran in its own session, on the pinned commit
- Every confirmed finding was read in the code by a person
- Plausible findings are still labelled plausible
- Every ranking has a stated reason
- The summary says what was checked and what was not
- The findings are stored with restricted access

## Output artifacts

- Findings register: ID, lens or lenses, location, label, priority, owner
- One-page summary: top findings, what was checked, what was not, and who reviewed
- Comparison note against the independent review, when it arrives

## Systems to update

- Engineering backlog: confirmed findings only, each with an owner
- RAID (risks, assumptions, issues, dependencies) log: top findings as open risks until fixed
- Security findings tracker, for the security lens

## Done when

Every finding has a label and a priority, confirmed findings have owners in the backlog, and the top of the list has been checked against at least one independent review.
