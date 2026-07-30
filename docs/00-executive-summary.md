# Executive Summary

_One page. The whole argument. Everything else in this repo is evidence for it._

## The situation

One person is currently the load-bearing element in two organizations with the
combined operating surface of about four companies:

- **Nightwatch** (`nightwatch-org`) — 13 years old, ~11 people, $64K MRR, 7+
  services (Rails + Go + Ember + React on Kubernetes, ClickHouse, Kafka,
  Sidekiq, 107,296 locations, 5 LLM providers), a repositioning in flight, a
  pricing migration to harvest, a 90-day MRR sprint, and **diligence ahead of a
  launch**. Constant processing/scalability pressure and a competitor set that
  changes weekly.
- **Formaviva** (`formaviva-org`) — the project that is actually loved, running
  four codebases (Rails API + three web front-ends + Flutter) on an
  **end-of-life stack** (Ruby 2.4 / Rails 5.1 / PG 9.6), with **no recurring
  revenue**, a take rate discounted toward zero, and manual payouts.
- **A personal life** that has never been given the same planning rigor as
  either.

## The single most important finding

**Both companies' own strategy documents independently diagnose the same root
cause — and it is not a market problem, it is a decision-making pattern.**

> Nightwatch: _"a technically excellent product trapped in a distribution
> problem — 800 customers after 13 years is a GTM failure, not a product
> failure."_ (`ai-docs/CONCLUSIONS.md`)

> Formaviva: _"Significant engineering energy has gone into rewrites — craft
> work — while the business model gap went unaddressed. Effort has been real
> but pointed at the wrong problem."_ (`docs/03-challenges.md`)

> Formaviva again: _"running a big-company product surface on a small-team
> budget."_ (`docs/03-challenges.md`)

Two independent analyses, two different businesses, one conclusion: **breadth
and craft are being chosen over focus and distribution, repeatedly.** That is
the pattern to fix. Fixing it at the personal level fixes it in both companies
at once; fixing it company-by-company will not hold, because the pattern
regenerates.

The corollary is uncomfortable and worth stating plainly: the exhaustion is not
caused by the market being hard. It is caused by carrying more surface than any
one person can carry — and most of that surface was voluntarily added.

## The four highest-level adjustments

1. **Adopt "finishability" as a value, on par with "exceptional work."**
   The Nightwatch value set (`docs/01-company/mission-values.md`) rewards
   Innovation, Exceptional Work ("we don't believe in good enough"), and
   Performance. It has **no value that limits scope**. That is exactly the
   value set that produces three web front-ends and a 30-document strategy
   backlog. Add the counterweight: _finish before starting; smallness is a
   feature._ See [`01-life-thesis.md`](01-life-thesis.md).

2. **Stop being the single point of failure at Nightwatch — deliberately, this
   quarter.** The MRR plan assigns the founder Levers 1 and 5 personally, plus
   product priority, plus positioning, plus diligence prep. That is not a plan;
   it is a queue with one server. Shed, delegate, or delete. See
   [`06-nightwatch-adjustments.md`](06-nightwatch-adjustments.md).

3. **Reclassify Formaviva from "business that must work" to "protected asset
   with a hard cap."** The honest read of `formaviva-org` is that the
   recommended pivot (Option B — membership) is _correct_ and _cannot be
   executed right now_ without taking the resources Nightwatch needs for
   diligence. The move is not to kill it and not to push it — it is to **cap
   it** (fixed money, fixed hours, security-only engineering, keep the
   editorial/radio part that is actually loved) and set a real decision date.
   See [`07-formaviva-adjustments.md`](07-formaviva-adjustments.md).

4. **Treat health as infrastructure with an SLA, not as leftover time.** The
   companies have a 99.98% uptime target and raw-HTML verifiability. The
   operator has neither a baseline nor a monitor. The immediate interventions
   are unglamorous and cheap: a sleep anchor, alerting boundaries after hours,
   exercise on the calendar as a meeting, and an actual medical baseline. See
   [`03-energy-and-health.md`](03-energy-and-health.md).

## What is actually draining the energy (and what to do)

| Drain | Real cause | Adjustment |
|---|---|---|
| "Constant processing/scalability problems" | Unit economics and reliability toil have **no owner and no number** — LLM spend is the fastest-growing variable cost with no baseline (`architecture.md`, `CONCLUSIONS.md` §10) | Assign one engineer as owner of cost-per-check and pager load; put a number on it weekly | 
| "Competitor density and constant changes" | Competitive monitoring is **continuous**, so the anxiety is continuous | Batch it: one monthly review, one doc, nothing in between. Compete on the 13-year data moat that does not reprice weekly | 
| Formaviva guilt | It is being judged as a business while being valued as an identity | Separate the two ledgers explicitly (joy budget vs business case) | 
| Decision fatigue | Numbers conflict across docs (€1.5M ARR vs $64K MRR); Formaviva's model is explicitly illustrative | **Get the two one-page P&Ls.** Uncertainty is a background energy tax | 
| Context switching | Two domains, two codebases-of-the-mind, same day | Day-level separation, not hour-level. Formaviva gets one bounded slot | 

## What to focus on in the future

In order, and only in this order:

1. **Ship the $64K → $75K quarter cleanly** — it is expansion-led, defensible,
   and it is the input to the diligence outcome that determines everything else.
2. **Convert the founder from operator to owner** — hire or promote the growth
   and delivery roles Nightwatch has been missing for years. This is the only
   permanent fix for the energy problem.
3. **Decide the Nightwatch endgame consciously** — write down what a good
   outcome actually looks like _before_ the process makes it urgent. See
   [`08-portfolio-strategy.md`](08-portfolio-strategy.md).
4. **Keep Formaviva alive and small** until that outcome resolves. Then, with
   resources and freedom, either fund it properly or hand it to someone who can.
5. **Use AI as the headcount that was never hired** — both repos already ship
   Claude skills. Adopt, do not build. See
   [`09-technology-leverage.md`](09-technology-leverage.md).

## The one-sentence version

**Nothing here is broken because the work is bad — it is breaking because one
person is carrying four companies' worth of surface, and the fix is subtraction:
cap Formaviva, de-bottleneck Nightwatch, put a number on the invisible costs, and
protect the body that is running all of it.**

---

_Start here, then read [`01-life-thesis.md`](01-life-thesis.md) (what you're
optimizing for), [`02-current-state.md`](02-current-state.md) (the honest
baseline), and [`../PLAN.md`](../PLAN.md) (what to do Monday)._
