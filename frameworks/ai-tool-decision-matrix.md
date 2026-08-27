# AI Tool Decision Matrix

**A sequencing guide for AI and DevOps tooling, ordered by return rather than by hype.**

Ratings current as of **August 2026**. Check that date before relying on any row. AI tooling moves
faster than any static document, and a matrix presented as current when it is eighteen months old
does more damage than no matrix at all.

---

## The order of operations

Most companies that have already bought an enterprise AI license are not getting return from it.
The reason is consistent: **they added intelligence to a broken system and got faster chaos.**

The companies that do get measurable return share one pattern. They fixed visibility, coverage, and
workflow automation first, then added the AI layer on top of a working foundation.

> **Do not buy the biggest model first. Buy the tools that show you what is broken. Then fix it.
> Then add AI.**

---

## Phase 1: Stop the bleeding

*Week 1 to 2, near zero cost.*

Find the problems you did not know you had. These tools generate the evidence that justifies
everything after them.

- **GitGuardian and GitHub Secret Scanning.** Credentials sitting in your repos right now. Deploys
  in a day, zero workflow change for developers.
- **SonarQube Community.** Technical debt you cannot see is debt you cannot pay. Free, CI
  integration in hours.
- **ESLint.** Already in most JavaScript and TypeScript stacks. Turn it on as a blocking CI gate.

## Phase 2: Build the floor

*Month 1 to 2, low cost.*

Reduce release risk with measurable outcomes. Engineers want these, because these are the ones that
eliminate the 2am pages.

- **Snyk.** Every pull request scanned for known CVEs, prioritized by exploitability.
- **Playwright.** An end-to-end suite that runs in CI. This is what makes deploying on a Friday
  a normal thing to do.
- **Codecov.** Makes coverage visible and trackable. Pairs naturally with Playwright.

## Phase 3: Workflow automation

*Month 2 to 3.*

Pick **one** manual workflow costing more than four hours per person per week. Automate it. Measure
the hours saved. Then pick the next one.

The discipline is the sequencing, not the tool. One workflow, proven, before the second. A team
that automates six things at once cannot tell you which one paid.

## Phase 4: The AI layer

*Month 3 to 6.*

Now you are ready. Clean code, tested releases, a known secrets posture, automated workflows. **The
AI augments a working system instead of amplifying a broken one.**

- **Claude (app and API).** Drafting, synthesis, spec writing, code generation. Start here.
- **Slack-native canvas automation.** Persistent briefings and multi-source aggregation, for teams
  already living in Slack.
- **Cursor.** Whole-repo context. Meaningfully better than file-level completion for refactoring.

## Phase 5: Evaluate and expand

*Month 6 and beyond.*

Return is now measurable, adoption is real, and you have internal champions. **Expansion is pull,
not push.** Evaluate enterprise LLM tiers, compliance automation, and runtime security based on
actual needs rather than vendor pitches.

---

## Why AI is phase 4 of 5

This is the part people argue with, so here is the reasoning stated plainly.

AI amplifies whatever process it lands on. Point it at a codebase with unknown secrets exposure, no
test coverage, and six manual handoffs, and you get the same mess produced faster and with more
confidence attached. **The phases before it are not prerequisites out of caution. They are what
makes the AI investment legible** - you cannot measure what a tool gave you if you could not measure
the baseline.

There is a second reason, and it is organizational. Phases 1 to 3 produce visible wins cheaply, and
those wins are what buys the credibility to spend real money in phase 4.

---

## The tool matrix

**Tier key:** `Use Now` · `Evaluate` · `Watch` · `Not Yet`

| Tool | Category | Problem it solves | Tier | Phase | Entry cost | Time to value |
|---|---|---|:---:|:---:|---|---|
| GitGuardian | Secrets detection | Credentials in repos, CI configs, Dockerfiles | Use Now | 1 | Free tier sufficient | 1 day |
| GitHub Secret Scanning | Secrets detection | Secrets committed to GitHub repos | Use Now | 1 | Included in GH Enterprise | Immediate |
| SonarQube Community | Code quality / SAST | Technical debt with no visibility | Use Now | 1 | Free | 1 to 2 days |
| ESLint | Code quality | Runtime JS/TS errors caught too late | Use Now | 1 | Free | Hours |
| Snyk | Dependency / SCA | Known CVEs sitting in dependencies for months | Use Now | 2 | Free tier generous | 30 min |
| Playwright | E2E test automation | No automated coverage, releases feel risky | Use Now | 2 | Free | 1 to 2 weeks |
| Codecov | Test coverage | No visibility into what is tested | Use Now | 2 | Free for public repos | 1 day |
| Semgrep | SAST | SAST findings too noisy to act on | Use Now | 2 | Free Community | 1 to 2 days |
| Make | Workflow automation | Data in five tools, status updates are manual theater | Use Now | 3 | ~$9/mo | 1 to 2 weeks |
| Zapier | Workflow automation | Simple trigger-action integrations, fast | Use Now | 3 | Free tier limited | Hours |
| Claude (app / API) | AI, general purpose | Manual drafting, synthesis, spec writing at scale | Use Now | 4 | ~$20/mo, API usage | Immediate |
| Slack canvas automation | AI, Slack-native | Status updates manual, signal aggregation ad hoc | Use Now | 4 | Vendor dependent | 1 to 2 weeks |
| Cursor | AI code editor | File-level completion, needs whole-repo context | Evaluate | 4 | ~$20/mo | Days |
| Vanta | Compliance automation | SOC 2 / HIPAA evidence collection is manual | Evaluate | 5 | Enterprise | 2 to 4 weeks |
| Perplexity | AI research | LLM research lacks citations | Evaluate | 5 | ~$20/mo | Immediate |
| tfsec / Checkov | IaC security | Infra misconfigs not caught until deployed | Evaluate | 5 | Free | 1 day |
| Trivy | Container security | Images with known CVEs reaching production | Evaluate | 5 | Free | Hours |
| Falco | Runtime security | No visibility into container behavior at runtime | Evaluate | 5 | Free (CNCF) | 1 to 2 weeks |
| Enterprise LLM tiers | AI, org-wide | Shadow AI, data governance, org adoption | Watch | 5 | Enterprise | Months |
| File-level code completion | AI, code | Individual-file developer productivity | Watch | 5 | ~$19/mo/dev | Days |
| Office-suite AI | AI, productivity | AI inside documents and spreadsheets | Not Yet | 5 | ~$30/mo/user | Variable |
| Autonomous SWE agents | AI, autonomous coding | Fully autonomous production code | Not Yet | - | TBD | 12 to 18 months |

### Notes on the contested rows

**Make over Zapier at real complexity.** Visual, non-developer friendly, wide connector library, and
it scales from simple triggers to multi-step conditional logic without a rewrite. Use Zapier for
simple flows and prototyping.

**Cursor over file-level completion for complex work.** The gap is refactoring and large codebases,
where whole-repo context is the whole game. For greenfield autocomplete the difference is small.

**Enterprise LLM tiers are `Watch`, not `Use Now`, and this is deliberate.** Buying org-wide before
the foundation exists is the single most common way to spend a lot and show nothing. **Audit shadow
AI use first.** You will find people already solving real problems with consumer tools, and that
usage map is a far better procurement input than a vendor's deployment guide.

**Autonomous coding agents are `Not Yet` on evidence, not on principle.** Benchmark numbers are not
production reliability. Watch the space, do not build a plan that depends on it.

**Compliance automation moves earlier in regulated environments.** In a HIPAA or SOC 2 context,
evidence automation is closer to phase 1 than phase 5, because audit readiness gates enterprise
sales. See the regulated-data guidance in
[security-program-playbooks](https://github.com/ChefPlex/security-program-playbooks).

---

## The one-paragraph version

Do not buy AI first. Buy visibility first. Find out where you are bleeding, then decide what plugs
the holes. The companies that get return from AI are not the ones who bought the biggest model. They
are the ones who had clean data, tested code, and automated workflows before they added the
intelligence layer.

---

**This matrix is a starting point, not a mandate.** The right tools depend on the current stack, the
team size, and where the pain actually is. Start with one, prove the return, then expand.
