# Decision Framework — How to Decide, So Deciding Stops Being Expensive

_Decision fatigue is one of the largest documented energy drains here. The fix
is not better judgment — the judgment is already good, as both strategy repos
demonstrate. The fix is making routine decisions **mechanical**, so that
judgment is spent only where it is actually needed._

---

## The five gates

Run any significant decision through these in order. Most decisions die at gate
1 or 2, which is the point — the value is in the cheapness of "no," not in the
sophistication of "yes."

### Gate 1 — Reversibility

> **Is this reversible? Then decide it fast and stop thinking about it.**

Most decisions are reversible and are being over-deliberated. A reversible
decision made quickly and corrected later costs less than a reversible decision
deliberated for three weeks. Copy changes, campaign tests, tooling, email
sequences, pricing experiments within an agreed range — all reversible. Decide
in minutes.

Irreversible decisions — hiring, firing, raising, selling, sunsetting a product,
public repositioning, taking on debt — get the full framework, a written
rationale, and a night of sleep. Nothing irreversible is ever decided while
tired, angry, or under artificial time pressure.

**The failure mode to watch:** applying irreversible-grade deliberation to
reversible decisions. That is what makes a week feel full while nothing ships.

### Gate 2 — Floor or ceiling?

> **Does this raise the floor, or does it raise the ceiling?**

The floor is health, runway, retention, reliability, security, and team
capacity. The ceiling is upside: new markets, new features, new tiers, new
companies.

**The ceiling has never been the binding constraint here.** A 13-year-old
profitable business with a real moat has plenty of ceiling. What has been thin
is the floor: capacity, focus, delegated ownership, and personal recovery.

So: **floor-raising work wins ties.** In practice this promotes churn work,
reliability, cost ownership, delegation, and hiring above another feature or
another channel — and that reordering alone resolves most competing priorities
without further debate.

### Gate 3 — What is being removed?

> **Nothing is added until something is removed.**

This is Deliberate Smallness made executable. Before saying yes to a feature, a
tier, a channel, a codebase, a commitment, or a company, name the thing being
removed to make room. If the answer is "nothing, we'll fit it in," the honest
translation is "this will be added to the founder's queue," and the answer is no.

This gate alone would have prevented the third web front-end, and it is the one
most likely to be skipped, because every individual addition is genuinely good.
**The additions are not the problem. The absence of a subtraction rule is.**

### Gate 4 — Who owns it, and is it you?

> **If the honest answer is "me," the decision is probably no.**

The founder is already the growth function, the product function, the strategy
function, the escalation point, and the second company. Any new work landing on
that queue makes the bottleneck worse, no matter how good the work is.

Three acceptable outcomes:
- **Someone else owns it** → proceed.
- **Nobody owns it, but it justifies a hire** → then the decision is a hiring
  decision, and that is the real conversation.
- **Nobody owns it and it does not justify a hire** → it is not important
  enough to do. Say so out loud and delete it.

### Gate 5 — What kills it, and by when?

> **Every yes carries a kill criterion and a date, written at the moment of the
> yes.**

Without a pre-written kill criterion, nothing is ever stopped — it is merely
starved, which is the worst of both outcomes: it still consumes attention and
guilt while producing nothing. This is precisely what has happened to the
Formaviva rewrites and to several strategy initiatives sitting at "⬜ not
started" in the tracker.

Format: _"We will do X. If by DATE we have not seen METRIC, we stop and do Y
instead."_ Both repos already model this well — Formaviva's 12-month decision
gate and Nightwatch's 90-day checkpoints. Extend the habit to everything,
including personal commitments.

---

## The pre-mortem question

For anything irreversible, before committing:

> **It is 12 months from now and this went badly. What happened?**

Then check whether the most likely failure is one you could survive. If the
answer is no, the decision is not "should we do this" but "how do we make it
survivable first."

Applied to the live decisions:

- **Nightwatch diligence/launch:** it goes badly, and the year was spent on
  process instead of product while the team drifted. Survivable — the business is
  profitable and bootstrapped. Mitigation: cap the time it is allowed to consume,
  and keep the 90-day operating rhythm running underneath it.
- **Formaviva Option B push now:** it goes badly, consuming 12 months of scarce
  engineering during diligence, and Nightwatch's number slips. **Not survivable
  at an acceptable cost** — which is exactly why [`07`](07-formaviva-adjustments.md)
  recommends capping rather than pushing.
- **Doing nothing about the founder bottleneck:** it goes badly, and 12 months
  from now everything is identical but with less energy in reserve. This is the
  **default path**, and its failure mode is the most likely of the three because
  it requires no decision at all.

---

## Standing decisions (already made — stop re-deciding these)

Re-litigating settled decisions is a large, invisible tax. These are closed.
Reopening one requires new evidence, not new mood.

| Decision | Status | Source |
|---|---|---|
| Nightwatch positioning: "Search Intelligence for the AI era" | **Locked** | `CONCLUSIONS.md` §1 |
| Peec is a tailwind, not an enemy. No adversarial copy. | **Locked** | `CONCLUSIONS.md` §6 |
| v4 pricing (€99/€199/€499/€1,499+, Legacy €49) | **Locked — do not redesign** | `FINAL-PRICING-TABLE.md`, `CLAUDE.md` |
| Grandfather protection is permanent; offers not forced migrations | **Locked** | `CLAUDE.md` |
| Growth is expansion/conversion-led, not CAC-led, pre-diligence | **Locked** | `MRR-SCALING-PLAN.md` |
| Formaviva: commission-only cannot reach break-even | **Settled** | `10-financial-model.md` |
| Formaviva: cannot out-Bandcamp Bandcamp | **Settled** | `05-positioning-verdict.md` |
| Formaviva: one web stack (Next.js); Ember read-only, Solid dropped | **Settled** | `07-execution-roadmap.md` |

**Anything on this list that comes up again gets one response: "already
decided," plus a pointer to the doc.** That is worth real energy per month.

---

## Decision debt

Undecided decisions are more expensive than wrong ones. They occupy attention
continuously, they block dependent work, and they never resolve on their own.

Rules:

1. **Anything undecided for more than two weeks gets forced.** Decide it, or
   explicitly defer it to a named date and remove it from active attention. A
   dated deferral is a decision; an open loop is not.
2. **Every open decision has an owner.** If the owner is you, it goes in an Owner
   block ([`04`](04-time-and-attention.md)), not into the gaps between meetings.
3. **Track them where they already are.** `MRR-EXECUTION-TRACKER.md` has a
   blocker/decision log with three items sitting at 🔴 open, including "confirm
   baseline metrics" and "is the payment-activation bug live in production."
   Those are not strategy questions — they are hours of work being carried as
   open loops for weeks. Force them first.

---

## Emotional-input filter

Some inputs generate strong reactions but contain no decision. Route them
accordingly rather than reacting to them:

| Input | Feels like | Actually is | Route to |
|---|---|---|---|
| Competitor launches a feature | Urgency | Data | Monthly competitive review |
| Competitor raises funding | Threat | Category validation — and, per the tailwind strategy, demand being created for you | Monthly review |
| A bad review or churned customer | Judgment | A retention data point | Churn analysis; batch it |
| A Formaviva slow month | Personal failure | Expected — there is no revenue model yet, by documented design | The cap; not the emotions |
| An incident at 23:00 | Emergency | Usually a morning problem | On-call rotation |

**The test:** does this input change a decision I would otherwise make? If not,
it is information, and information can wait for its scheduled block. Most of the
"competitor density" drain dissolves under this filter, because almost none of it
changes a locked strategy.

---

## The one-line version

> **Decide reversible things fast. Raise the floor before the ceiling. Subtract
> before adding. Refuse anything that lands on your own queue. Write the kill
> date at the moment of the yes.**
