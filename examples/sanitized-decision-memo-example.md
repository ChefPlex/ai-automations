# Sanitized Decision Memo Example

## Decision needed

Choose the rollout approach for the encryption migration across the remaining services.

## Background

The program is migrating a set of services to a new encryption control model. Initial migration testing is complete for three services, while two services remain uncommitted. The current milestone is still achievable, but the remaining window is tight enough that the rollout approach needs a decision this week.

## Options considered

| Option | Summary | Pros | Cons |
|---|---|---|---|
| Option A | Continue with service-by-service rollout | Lower operational risk, easier rollback | Slower completion, longer validation window |
| Option B | Batch remaining services into one rollout | Faster completion, simpler milestone tracking | Higher operational risk, harder rollback |
| Option C | Delay remaining services to next quarter | Reduces near-term pressure | Misses target milestone, extends compliance exposure |

## Recommendation

Proceed with Option A and set a firm commitment date for the two remaining service teams. This preserves operational safety while keeping the milestone achievable.

## Tradeoffs

Option A is slower than a batch rollout, but it reduces operational and rollback risk. Option B may improve timeline optics, but it introduces higher execution risk at the exact point where validation evidence needs to be clean. Option C reduces pressure now, but it moves the risk into next quarter and creates a compliance gap the program is trying to close.

## Decision owner

Engineering Director

## Needed by

Friday

## Consequence of no decision

The team will continue with partial commitments, which may compress validation and create an avoidable escalation later in the quarter.

## TPM note

The recommendation is not the fastest path. It is the safest path that still protects the milestone.
