# AI Prototyping Sandbox Workflow

## Goal

Let people who do not write code for a living (product, operations, support, QA [quality assurance]) build working prototypes with AI against the real application, without any of that work reaching production unreviewed.

The usual first instinct is to ban AI coding tools for non-engineers. That does not stop the work. It moves it to a personal laptop, against a copy of the code nobody knows exists, using whatever tool was easiest to sign up for. People take the easiest path, so the sandbox makes the safe path the easiest one.

Think of it as a test kitchen. Anyone can cook in it. Nothing goes out to the dining room until the chef has tasted it.

In terms of the [execution tiers](../frameworks/ai-execution-tiers.md), the person decides what should exist and the AI builds it (tier 3). An engineer's review of a draft pull request is the tier-4 gate before anything merges.

## The controls

Five controls. The first four apply inside the sandbox. The fifth applies before any tool is let in.

| Control | What it means | Why |
|:---|:---|:---|
| **Isolated branches** | Every prototype lives on its own branch, cut from main and named for the person and the change. Nobody in the sandbox can merge. | A bad prototype costs one branch. Delete it and nothing else is affected. |
| **Draft pull requests only** | Work leaves the branch only as a draft PR (pull request). An engineer decides whether it becomes real work, gets rebuilt, or closes. | The prototype is a specification someone can click through. Engineers decide what ships. |
| **Presentation layer only** | Changes stay in screens, copy, layout and front-end logic. No database schema, authentication, API (application programming interface) contracts, infrastructure or secrets. | Most of what non-engineers want to change is here, and a mistake here is easy to see and undo. |
| **Intent captured before work starts** | A short written statement of what the person wants to change and why, filed before the first prompt. | Without it, a reviewer judges a diff without knowing the question it was meant to answer. |
| **AI tools vetted offline first** | Any new coding assistant, plugin or agent is tried on a throwaway repository with no secrets and no real data before it is pointed at the real code. | The vetting answers what the tool sends out, where it sends it, what it can run, and what it writes. Small plugins get the least scrutiny and often the broadest access. |

## Source systems

- Source control: branch protection, draft PR settings, a code-ownership file
- The intent log: a form, a ticket queue or a file in the repository, as long as it is one place
- The AI tool register: the inventory in the [AI Governance Program Template](../frameworks/ai-governance-program-template.md)

## Inputs to gather

Before the first sandbox session:

- The directories that count as the presentation layer, written down as paths
- The engineers who review sandbox PRs, by name, and the turnaround they commit to
- The approved AI tools, each with the date it was vetted
- The test data rules: what data a prototype may display

## Safety checks

- Main is protected. No direct pushes, and every merge needs an engineer's approval.
- A path check in the tooling flags any change outside the approved directories for code-owner review. A wiki page asking people to stay inside them is not enough.
- The sandbox environment holds no production credentials. Use test accounts and synthetic or de-identified data.
- No regulated or personal data in prompts, screenshots or test fixtures. See [Safety and Data Handling](../safety-and-data-handling.md).
- The tool in use is on the approved list, at the vetted version.

## Intent capture template

```text
INTENT (fill in before the first prompt)

Name / team:
Branch:
What I want to change (one sentence):
Who it is for, and the problem they hit today:
How a reviewer will know it worked:
What I will not touch:
AI tool and version:
Date:
```

It takes about five minutes. If the person cannot fill in "how a reviewer will know it worked", the prototype is not ready to start. That conversation is much cheaper before the AI writes 400 lines than after.

## Prompt sequence

1. Paste the intent statement as the first message of every session, not only the first one.
2. Ask the tool to restate the change and list the files it expects to touch. Stop if any file is outside the approved paths.
3. Build in small steps, and run the application after each one.
4. Before opening the draft PR, use the final prompt below to write the description.

## Final prompt

```text
Write a draft pull request description for the change on this branch.

Use the intent statement below. Include:
1. What changed, in plain language, for a reviewer who did not see this session
2. Every file changed, and confirm each one is inside these approved paths: [paths]
3. Steps a reviewer can follow to see the change running
4. What was not tested
5. Anything you were unsure about or guessed at

Do not describe the change as ready to merge. Do not say tests passed unless
they ran in this session.

Intent:
[paste the intent statement]
```

## Where this fails

**The review turns into a rubber stamp.** Prototypes built with AI often look finished. That is exactly when a reviewer stops reading. Hold the engineer review to the tier-4 rules in the [execution tiers](../frameworks/ai-execution-tiers.md#tier-4---ai-drives--humans-review): saying no is cheap, the reviewer is named, and the catch rate is measured.

**Engineers ignore the queue.** If draft PRs sit for two weeks, people stop opening them and go back to building on their laptops. Name the reviewer and the turnaround they commit to, then track it like the other controls.

**The boundary leaks one field at a time.** A screen change needs one new field, and the field needs a schema change. The path check catches the file. Whether the field should exist at all is an engineering decision.

**Intent capture is filled in afterwards.** Compare the date on the intent with the first commit on the branch.

**Offline vetting is skipped for "just a plugin".** Ask the same questions of a browser extension that you ask of a coding agent.

The sandbox controls what reaches the codebase. It cannot stop someone pasting code into an unapproved tool at home. The best answer so far is to keep the approved path fast enough that nobody needs another one.

## Human review checklist

- Intent filed before the first commit
- Every changed file inside the approved paths
- Tool on the approved list
- No real data in screenshots, fixtures or prompts
- Reviewer understands what the prototype was for
- Decision recorded: rebuild as real work, merge after changes, or close

## Output artifacts

- Intent log entry
- Draft PR with description
- Reviewer decision, with the reviewer's name

## Systems to update

- Intent log
- Engineering backlog, if the prototype becomes real work
- AI tool register, for any new tool request

## Done when

Every prototype has an intent statement, a draft PR, and a decision recorded by a named engineer, and nothing from the sandbox has reached main without all three.
