# Sanitized Launch Readiness Example

## Launch summary

The launch introduces a new platform control for a defined set of internal services. The target launch date is next Wednesday, pending completion of monitoring validation and support runbook sign off.

## Readiness status

| Area | Status | Notes |
|---|---|---|
| Product readiness | Green | Scope approved |
| Engineering readiness | Yellow | Final service validation pending |
| Security readiness | Green | Control review complete |
| Reliability readiness | Yellow | Monitoring dashboard not yet validated |
| Support readiness | Yellow | Runbook in final review |
| Documentation | Green | Internal docs drafted |
| Rollback plan | Green | Rollback steps validated in staging |

## Open blockers

| Blocker | Owner | Needed by |
|---|---|---|
| Monitoring dashboard validation | Observability owner | Monday |
| Support runbook sign off | Support lead | Tuesday |

## Top risks

| Risk | Impact | Mitigation |
|---|---|---|
| Monitoring gap at launch | Slower detection of post-launch issues | Complete dashboard validation before go decision |
| Support runbook not approved | Support team may not have clean handoff | Final support review scheduled for Tuesday |

## For the decision owner

The evidence supports go only if two items close: monitoring validation by Monday and support runbook sign off by Tuesday. If either slips, the evidence points to moving the launch rather than launching with known operational gaps. The go or no go call is the decision owner's.

## TPM note

The decision owner is not looking at a vague "mostly ready". They are looking at two named gates with dates.
