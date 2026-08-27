# The Activity Mapping Method

**How to find out where AI actually belongs in your company, in about a week, without buying anything.**

Most AI adoption starts with a tool and looks for uses. This starts with the work and looks for
where a tool would help. The output is a map: every activity the business performs, each one
assigned an execution tier, an owner, and a tool.

The map is not the point. **The conversations that produce it are the point.** Two people who both
say "we use AI for hiring" find out they meant different things, and they find out in a
classification meeting rather than in an incident review.

---

## Three levels of resolution

Stop at the level where the answer changes what someone does on Monday.

```
L1  FUNCTION      Where does AI belong across the business?
    9 functions x ~6 activities, each assigned a tier
        |
        v
L2  ACTIVITY      Inside this function, which steps, which owner, which tool?
    each L1 activity -> ~6 sub-activities
        |
        v
L3  WORKFLOW      How does this actually run, gate by gate?
    each L2 phase -> 6-7 sub-streams x 5-6 steps, human gate named
```

**Most organizations need L1 and L2 only.** L1 takes a day. L2 takes two or three. Together they
are enough to decide what to buy and what to change.

**L3 is expensive and worth it in exactly one situation:** where the cost of getting a step wrong
is high and the step is currently undefined. In practice that means the functions with gates in
them. Security review, release decisions, incident response, anything with a regulator attached.
Building L3 for marketing content production is precision applied to a problem that did not need it.

---

## L1: the function map

**Nine functions cover most technology companies.** Product, Engineering, Marketing, Revenue,
Customer Success, Investor Relations, Legal, Finance, People. Use your own if they differ, but
resist inventing new ones during the exercise. The point is to classify the work, not to redesign
the org chart.

For each function, list roughly six activities at the level a department head would recognize.
"Research market and user needs." "Configure security and compliance." "Run payroll." Not tasks,
not job titles. **Activities.**

Then assign each one a tier. One tier, no ranges.

**What good looks like at L1:** one page, colour-coded, and someone who does not work at the
company can read it and tell you where the humans are.

### Do the tier 1 column first

Before classifying anything else, go through every activity and mark the ones where a human decides,
alone, always. Hiring decisions. Architecture tradeoffs. Go/no-go calls. Investor conversations.
Difficult performance conversations.

**Draw that boundary before you know what it will cost you.** It is much easier to defend a line
you drew on principle than one you drew after someone showed you the savings from crossing it. A
map with an empty tier 1 column is not an efficient company. It is a company that has not thought
about this.

---

## L2: the activity map

Take one function. Explode each L1 activity into the five or six sub-activities that actually
happen. For each, record four fields:

| Field | Why it matters |
|---|---|
| **Tier** | The decision itself |
| **Owner** | A named role. Not a team. "Engineering reviews it" means nobody reviews it |
| **Tool** | Named specifically. "AI" is not a tool. "Claude for the draft, human edit" is |
| **Gate** | For tiers 4 and 5: who can stop it, or an explicit "nobody, and here is why" |

**Do this with two people who do the work, not one person who owns the org chart.** Where they
disagree about the tier, you have found an undefined process, and you found it for the price of a
conversation.

**Expect the map to be wrong in useful ways.** The common finding is not "we should automate this."
It is "three people are doing this differently and none of them knew."

---

## L3: the workflow map

Only where the gates matter. Take one L2 phase and break it into sub-streams, then into steps, and
for every step name the tool, the owner, and where the human gate sits.

The value of L3 is not the diagram. It is that **you cannot draw it without discovering that a gate
you believed existed does not.** That discovery is the entire return on the exercise, and it is
common enough to expect.

---

## Running it: a week

| Day | Work | Output |
|---|---|---|
| **1** | List functions and activities. Do not classify yet | The L1 skeleton |
| **2** | Tier 1 pass. What must stay human, decided on principle | The boundary |
| **3** | Classify the rest. Two people per function, disagreements logged | The L1 map |
| **4-5** | L2 on the two or three functions with the most pain | Activity maps with owner, tool, gate |
| **later** | L3 only where a gate is load-bearing and currently vague | Workflow maps |

**The disagreement log is a real deliverable.** Every activity where two practitioners assigned
different tiers is an undefined process. That list is more actionable than the map.

---

## What to do with the finished map

**Do not go shopping.** The map tells you where the work is, not what to buy, and a map is not a
budget request. Sequencing what to adopt is a separate exercise with its own order of operations,
and the order matters more than the tools.

Three things the map is immediately good for:

1. **Finding the tier-4 gates that have become rubber stamps.** Any gate approving everything for a
   quarter is a log, not a gate.
2. **Finding silent tier-5 automations.** Anything running unattended whose failure nobody would
   notice is worse than the manual step it replaced.
3. **Finding the work that was never worth a person's attention.** Which is the point. The time
   goes back to the judgment work that was getting squeezed.

---

## Re-run it

**A map is a snapshot and it goes stale.** Tools change, the team changes, and activities drift up
and down the ladder without anyone deciding they should. Re-run L1 every six to twelve months. It
takes a day the second time.

**Watch for drift toward the bottom.** Activities migrate from tier 3 to tier 4 to tier 5 quietly,
one convenience at a time, and nobody makes a decision to stop reviewing something. They just stop.
The re-run is where that gets caught.
