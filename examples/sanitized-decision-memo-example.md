# Sanitized Decision Memo Example

## Decision needed

Choose the rollout approach for the encryption migration across remaining services.

## Background

The program is migrating a set of services to a new encryption control model. Initial migration testing is complete for three services, while two services remain dependent on local service owner readiness.

## Options considered

| Option | Summary | Pros | Cons |
|---|---|---|---|
| Option A | Continue with service by service rollout | Lower operational risk, easier rollback | Slower completion, longer validation window |
| Option B | Batch remaining services into one rollout | Faster completion, simpler milestone tracking | Higher operational risk, harder rollback |
| Option C | Delay remaining services to next quarter | Reduces near term pressure | Misses target milestone, extends compliance exposure |

## Recommendation

Proceed with Option A and set a firm commitment date for the two remaining service teams. This preserves operational safety while keeping the milestone achievable if the remaining teams confirm their rollout windows this week.

## Tradeoffs

Option A is slower than a batch rollout, but it reduces operational and rollback risk. Option B may improve timeline optics but introduces higher execution risk. Option C should only be used if service owners cannot commit by the decision deadline.

## Decision owner

Engineering Director

## Decision deadline

Friday

## Consequence of no decision

The validation window may compress, and the program may need an executive level milestone risk decision.
