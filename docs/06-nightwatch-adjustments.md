# Nightwatch — Adjustments From the Personal Perspective

_The business strategy in `nightwatch-org` is sound and does not need rewriting.
This document is about the **operator-level** changes: what to stop carrying
personally, how to make the invisible costs visible, and how to make the
competitive noise stop consuming energy. Nothing here contradicts
`MRR-SCALING-PLAN.md` — it is what makes executing it survivable._

---

## What is already right (leave it alone)

- **The positioning** — "Search Intelligence for the AI era," Peec as a tailwind.
  Locked, correct, and generous. Do not reopen.
- **The pricing** — v4 is live. `CLAUDE.md` is explicit: harvest it, do not
  re-litigate it.
- **The 90-day plan** — expansion-led, defensible, diligence-appropriate. Lever 1
  (legacy migration) really is the highest-certainty money in the building.
- **The moat** — 13 years of SERP data, raw HTML for every check, and Citation
  Intelligence as the correlation only Nightwatch has both datasets to compute.

**The strategy is not the problem. The strategy is done. The problem is that
one person is the execution layer for most of it.**

---

## Adjustment 1 — Take the founder off the critical path (the only permanent fix)

### The problem, stated precisely

Reading `MRR-SCALING-PLAN.md` and `team.md` together:

- Lever 1 (migrate/upsell the legacy base, +$4,500) — **Owner: Founder + CS**
- Lever 5 (5–8 demos/week, +$3,000) — **Owner: Founder**
- Marketing function — _"appears to be founder-driven"_
- Product priority, positioning, Citation Intelligence scope — founder
- Diligence preparation — founder
- Escalation point for engineering and support — founder
- Plus a second company

That is not an aggressive plan; it is a **single-server queue**, and the queue
is the actual constraint on the quarter. Every lever competes for the same
person. If that person has a bad two weeks, the quarter misses — and there is no
redundancy anywhere in the design.

### The adjustments

**a) Name a growth owner who is not you — this quarter.**
`CONCLUSIONS.md` lists Head of Growth as a Tier-2 gap and defers hiring to
Phase 3. **That deferral is the mistake, and the risk table in
`EXECUTIVE-SUMMARY.md` already says so** — it lists "founder bottleneck" as
*high probability* and recommends hiring VP Marketing in Phase 2, not Phase 3.
The bottleneck is not at $5M ARR; it is now.

Cheapest viable versions, in order of speed:
- **Promote internally.** Izabela already owns outreach and support. Growth
  execution ownership, with founder coaching, is a smaller step than a hire and
  starts immediately.
- **Fractional Head of Growth**, 2 days/week. Faster than a full search, far
  cheaper than the founder's time, and reversible (Gate 1).
- **Full hire** — right, but slow. Start the search; do not wait for it.

**This is one senior owner with agent leverage — not a growth team.** Under the
AI-first model ([`09`](09-technology-leverage.md)), the production work
(content, sequences, lists, research) belongs to skills, so this role is scoped
as *ownership of the number* rather than as a headcount multiplier. What AI
cannot do is the reason this item exists: hold accountability, decide, and take
the escalations off the founder's desk.

**b) Split Lever 1 off the founder entirely.**
The migration/upsell campaign is the highest-certainty MRR in the plan and it is
mostly systematic: cohort the base, send the sequence, run the calls. The
`migration-upsell` skill already encodes pricing, cohorts, and tone. CS can own
the sequence and the majority of the calls; the founder takes only the largest
accounts. **Founder involvement should scale with account size, not apply
uniformly.**

**c) Keep only demos on the founder — and batch them.**
Founder-led demos are genuinely differentiated and convert at 25–30%. Keep them.
But 5–8 demos/week belongs in **two afternoon blocks**, not scattered across
five days destroying five mornings ([`04`](04-time-and-attention.md)).

**d) Route alerts away from the founder by default.**
On-call rotation with a defined escalation bar. Escalation to the founder should
be a human decision, never a default config. This is both a health intervention
and a delegation forcing-function: engineers who cannot escalate to the founder
by default start owning outcomes.

**e) Move one item off your permanent list every Monday.**
Twelve items per quarter, five minutes a week ([`04`](04-time-and-attention.md)).
This is the compounding version of de-bottlenecking, and it works even in weeks
where nothing else does.

---

## Adjustment 2 — Give the processing/scalability pain an owner and a number

### The problem underneath the symptom

The recurring processing and scalability problems are **normal** for this
architecture — millions of keywords daily across ClickHouse, Kafka, Sidekiq, and
Kubernetes, plus 5 LLM providers, will always generate incidents. That is the
cost of the moat.

What makes them *draining* rather than merely operational is that they arrive
attached to an unanswered economic question. From the repo's own documents:

- LLM API costs are _"the fastest-growing variable cost"_ — with **no measured
  baseline** (`architecture.md`).
- `CONCLUSIONS.md` §10 admits a **40% AI-cost reduction was assumed for margin
  math with no plan to achieve it**, and asks openly whether the stack can handle
  3× traffic.
- Cost-optimization initiatives (LLM routing, caching, batching, ClickHouse
  tuning) are listed as "current" but have **no named owner and no target**.

So every incident silently re-raises: _are we getting more expensive faster than
we are growing?_ Unanswered questions of that shape are what actually exhaust
people — far more than the incidents themselves.

### The adjustments

**a) One named owner for unit economics and reliability.** Not a committee, not
"engineering." One person whose scoreboard is:

| Metric | Why it matters |
|---|---|
| Cost per tracked keyword per month | The core unit economic |
| Cost per AI prompt, by model | The fastest-growing variable cost |
| Blended gross margin | The number diligence will ask about |
| Pager events / week, and % out-of-hours | The toil number — the one that costs people |
| Sidekiq backlog p95 | The documented leading indicator of processing pain |

**b) Put it on one page, weekly, next to the MRR tracker.** A cost you can watch
falling is a completely different psychological object from a cost you suspect is
rising. Most of the anxiety here is about *not knowing*, not about the number.

**c) Convert cost pressure into product structure, not heroics.** The pricing
work already contains the mechanism: soft caps with overage billing (Lever 6),
prompt allowances per tier, and AI bundled into tiers. Heavy users should become
expansion revenue rather than a margin leak or a support ticket. **This is a
pricing lever, not an engineering-effort lever** — and it is already agreed.

**d) Treat reliability toil as a first-class backlog item.** If out-of-hours
pages are non-trivial, that is a roadmap item with a target, not a personality
trait of the system. Halving it is worth more to sustainable capacity than most
features.

**e) Answer the 3× question deliberately, once.** A short, written capacity
assessment — where the stack breaks at 3× and what it costs to fix — closes an
open loop that is currently being carried indefinitely, and it is a diligence
asset regardless.

---

## Adjustment 3 — Make competitor density a scheduled input, not an ambient condition

### The problem

`peec-as-tailwind-strategy.md` and `CONCLUSIONS.md` §6 already settled this:
Peec is the category pioneer, Nightwatch is the graduation destination, no
adversarial copy, ride the $29M of market education. **The decision is made.**

But monitoring continues continuously, and continuous monitoring of a
fast-moving category produces continuous low-grade threat response. The category
will keep moving whether or not it is watched; watching it daily changes nothing
except the watcher's nervous system.

There is also a real risk of strategic drift: constant exposure to competitor
launches creates pressure to respond feature-by-feature, which is the reactive
posture the tailwind strategy was explicitly designed to avoid.

### The adjustments

**a) One monthly competitive review.** One block, one document, distributed to
the team. Nothing in between — no daily checking, no evening scrolling, no
phone.

**b) Delegate the monitoring itself.** This is exactly what an AI-assisted
digest is for ([`09`](09-technology-leverage.md)) and it mirrors what
`formaviva-org` already does with the `scene-radar` skill. The founder should
read a monthly summary, not perform continuous surveillance.

**c) Compete on what does not reprice weekly.** Feature parity is a treadmill
against a $29M-funded competitor. Thirteen years of SERP data, raw HTML
verifiability, and Citation Intelligence are not. `CONCLUSIONS.md` is right that
Citation Intelligence is the one thing that must ship well — because it is the
only differentiator that competitors cannot buy their way to quickly, since they
lack the datasets.

**d) Apply the emotional-input filter** ([`05`](05-decision-framework.md)): a
competitor's launch or raise changes no locked decision. It is information, and
information waits for its block.

---

## Adjustment 4 — Protect the quarter from scope creep

The 90-day plan explicitly lists what it is *not* doing: no re-litigating
pricing, no paid acquisition at scale, no betting the quarter on Citation
Intelligence, no big-bang launches. **That list is the most valuable part of the
plan and it will be under pressure all quarter.**

Add three operator-level protections:

1. **No new product surface for 90 days.** Nothing new starts until the number
   is hit or the quarter closes. Gate 3 applies without exception.
2. **The diligence process gets a time box.** Diligence expands to fill
   available attention. Cap the hours per week it is allowed to consume and keep
   the operating rhythm running underneath it. A business that stops operating
   during diligence produces worse diligence.
3. **Citation Intelligence ships in parallel, on its own track, with its own
   owner.** It is the 3-month positioning moat, explicitly *not* the 90-day MRR
   engine. Do not let it absorb the quarter, and do not let the quarter starve it.

---

## Adjustment 5 — Close the three open loops in the tracker this week

`MRR-EXECUTION-TRACKER.md` has three items sitting at 🔴 open. None is a strategy
question; all are hours of work being carried as background load:

| Open item | Real cost | Fix |
|---|---|---|
| Confirm baseline metrics (customers, ARPA, churn, conversion, legacy cohorts) | **Every lever is sized on assumptions** | Hours in Stripe + PostHog |
| Payment-activation bug: live in production? | Users who **already decided to pay** may be failing to pay, right now | One test transaction |
| Enable marketplace plugins | Blocks the execution horsepower the plan assumes | One decision |

**The payment bug is the single highest-return item in either repository.** The
plan calls it Sprint 0, Day 1 — days of engineering for immediately recovered
revenue, zero downside, and a bug that would be a credibility hit if it surfaced
during diligence. It has been open long enough to appear in a tracker as an
unverified assumption. Drive a real card through the flow this week.

---

## The scoreboard for these adjustments

Not MRR — that is already tracked. These measure whether the **operator-level**
changes actually happened:

| Adjustment | Measure | Target this quarter |
|---|---|---|
| Founder off critical path | Levers owned personally by founder | From 2+ → 1 (demos only) |
| Growth ownership | Named non-founder growth owner | In place |
| Unit economics visible | Weekly cost-per-check on one page | Live by week 4 |
| Toil reduced | Out-of-hours pages to founder | → 0 by default routing |
| Competitive noise | Competitive research sessions | 1/month, batched |
| Open loops | 🔴 items in the tracker | 3 → 0 by week 2 |
| Scope discipline | New product surface started | 0 |
