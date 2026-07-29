# Current State — The Honest Baseline

_What is actually being carried, what it costs, and what is unknown. Every claim
traces to a source document so it can be argued with rather than absorbed._

---

## The load, laid out

### Nightwatch (`nightwatch-org`)

| Dimension | Reality | Source |
|---|---|---|
| Age / stage | 13 years, bootstrapped, profitable | `ai-docs/EXECUTIVE-SUMMARY.md` |
| Revenue | **$64K MRR** live figure (other docs quote ~€1.5M ARR / ~800 customers as "rounded/aspirational") | `ai-docs/MRR-SCALING-PLAN.md` |
| Team | ~11 people; **no marketing lead, no Head of Growth, no CSM, no AEs** | `docs/01-company/team.md` |
| Services | Ember web, React assistant, Go gateway, Rails API, Go proxy, SERP engine, AI tracking service | `docs/03-engineering/architecture.md` |
| Data infra | ClickHouse + Postgres + Kafka + Sidekiq/Redis + raw HTML for every check, on Kubernetes | same |
| Scale | Millions of keywords daily, 107,296 locations, 5 LLM providers | same |
| Fastest-growing cost | **LLM API spend — with no measured baseline** | `architecture.md`, `CONCLUSIONS.md` §10 |
| In flight | Repositioning, v4 pricing migration, Citation Intelligence (3-month target), 90-day MRR sprint, SOC2 path | `CONCLUSIONS.md` |
| Context | **Diligence ahead of a launch** — growth must be clean and defensible | `MRR-SCALING-PLAN.md` |

### Formaviva (`formaviva-org`)

| Dimension | Reality | Source |
|---|---|---|
| What it is | Curated, invite-only platform for underground electronic music | `docs/01-product-overview.md` |
| Revenue model | Commission defaulting to 10%, **discounted toward 0** ("no charge for creators"); **no recurring revenue live** | `docs/02-why-not-profitable.md` |
| The math | Braintree (~2.9% + €0.30) can earn more per sale than the platform does | same |
| Codebases | Rails API + **three** web front-ends (Ember, Next.js, Solid) + Flutter mobile | `docs/03-challenges.md` |
| Stack | **Ruby 2.4 / Rails 5.1 / PostgreSQL 9.6 — all end-of-life** | same |
| Payouts | Manual, via Retool; platform holds sellers' funds in one merchant account | `docs/02-why-not-profitable.md` |
| Break-even | ~150 Pro artists + ~500 paying fans (membership model) vs €40–80K/mo GMV (commission model) | `docs/10-financial-model.md` |
| Recommended path | Option B — membership + toolkit, ~12 months of execution | `docs/06-pivot-options.md` |
| Emotional role | **The project that is loved.** Not incidental — this is why it is still here | user |

### The person

| Dimension | Reality |
|---|---|
| Role at Nightwatch | CEO/founder, product vision, strategy — plus, per the MRR plan, personally owning Lever 1 (migration/upsell) and Lever 5 (5–8 demos/week) |
| Role at Formaviva | Approvals, revenue-share deals, payouts route through a small number of people — a documented bus-factor risk (`docs/03-challenges.md`) |
| Marketing function | "appears to be founder-driven" (`nightwatch-org/docs/01-company/team.md`) |
| Documented drains | Processing/scalability problems, competitor density and constant change, an unprofitable loved project |
| Health status | **Unknown — no baseline exists.** This is itself a finding |

---

## The energy audit: what is actually costing what

The stated drains are real, but each has a cause underneath it that is more
tractable than the symptom. This table is the core diagnostic of the repo.

### 1. "Constant problems with processing and scalability"

**Underneath it:** these are not unusual engineering problems. Millions of
keywords daily across ClickHouse/Kafka/Sidekiq on Kubernetes _will_ produce a
steady stream of incidents — that is the normal cost of the architecture. What
makes it draining is not the incidents, it is that **the cost of running it has
no owner and no number.**

The architecture doc names LLM API spend as the fastest-growing variable cost
and lists caching, routing, and batching as "current initiatives."
`CONCLUSIONS.md` §10 admits the 40% AI-cost reduction was **assumed for margin
math with no plan to achieve it**, and asks openly whether the stack can handle
3× traffic. So every incident carries an unresolved economic question with it,
and unresolved questions are what actually exhaust people — not work.

**The adjustment:** a named owner, a weekly number (cost per tracked keyword,
cost per AI prompt, pager events per week), and a trend line. A cost you can see
falling is a completely different psychological object from a cost you suspect
is rising.

### 2. "Competitor density and constant changes"

**Underneath it:** the strategy is already correct and already decided —
`peec-as-tailwind-strategy.md` concluded that Peec is a tailwind and Nightwatch
should be the graduation destination, and `CONCLUSIONS.md` locked it. **The
decision is made. The monitoring is what continues.**

Continuous monitoring of a fast-moving competitive set produces continuous
low-grade threat response, which produces the feeling of never being safe, which
is exactly what "competitor density" describes emotionally. The category will
keep moving whether or not it is watched daily; watching it daily changes
nothing except the watcher.

**The adjustment:** batch it. One monthly competitive review producing one
document, and nothing between reviews. And keep competing on the thing that does
not reprice weekly: 13 years of SERP data, raw HTML verifiability, and Citation
Intelligence — a correlation only Nightwatch has the datasets to compute.

### 3. Formaviva

**Underneath it:** it is being **measured on the wrong ledger.** It is judged as
a business (where it fails clearly and the repo says so in detail) while its
actual value is identity, creative renewal, and standing in a scene that
matters. Those two ledgers have been merged, so every look at Formaviva returns
"failing," and something loved that constantly reports failure becomes a source
of guilt rather than of energy.

**The adjustment:** split the ledgers formally. A joy budget with a cap, and a
separate business case with a real decision date. Detailed in
[`07-formaviva-adjustments.md`](07-formaviva-adjustments.md).

### 4. Decision fatigue from unreliable numbers

**Underneath it:** the baseline is not known.

- Nightwatch quotes both **~€1.5M ARR / 800 customers** and **$64K MRR**
  (≈$768K ARR). `MRR-SCALING-PLAN.md` explicitly reconciles this by calling the
  former "rounded/aspirational" — but the reconciliation lives in one doc while
  the larger number lives in several.
- The `MRR-EXECUTION-TRACKER.md` baseline table is **entirely unconfirmed**:
  customer count, legacy base size, trial conversion, churn, ARPA and even
  whether the payment-activation bug is live in production are all marked
  "assumptions until confirmed from Stripe/PostHog."
- Formaviva's financial model carries an explicit warning: _"⚠️ Calibrate before
  trusting… illustrative planning figures, not audited actuals."_

**Every strategic decision currently being made is being made on estimates.**
That is a permanent background tax: it makes every decision feel heavier than it
is, and it makes it impossible to ever feel finished, because nothing can be
confirmed. This is the cheapest fix in the entire repo and it is not an
engineering project — it is a few hours in Stripe and PostHog.

### 5. Context switching between two domains

**Underneath it:** B2B SaaS growth and underground music curation share nothing
— not vocabulary, not tempo, not success criteria. Switching between them inside
a single day pays the full re-entry cost twice, both directions.

**The adjustment:** separate at the **day** level, not the hour level. Formaviva
gets one bounded, protected slot; Nightwatch does not get to bleed into it and
it does not get to bleed into Nightwatch.

---

## What is genuinely working (do not accidentally break these)

Subtraction is the theme of this repo, so it is worth being explicit about what
must survive it:

- **Product quality at Nightwatch** — 4.8/5, 99.9% rank accuracy, a loyal base.
- **A real, hard-to-copy moat** — 13 years of SERP data plus raw HTML storage
  for every check. Not reproducible by a well-funded 12-month-old competitor.
- **Bootstrapped and profitable** — no investor clock. This is the single
  greatest source of freedom available and it should be spent on _optionality_,
  not on proving something.
- **A correct, already-decided strategy** in both companies. Neither needs
  another strategy document. Both need execution and subtraction.
- **A trusted curatorial brand and real artist relationships** at Formaviva —
  the asset worth more repositioned than liquidated.
- **A capable, long-tenured team** at Nightwatch.

---

## The unknowns that matter most

Ranked by how much they are currently distorting decisions:

| # | Unknown | Why it matters | Cost to resolve |
|---|---|---|---|
| 1 | Real Nightwatch baseline (customers, ARPA, churn, conversion, legacy cohort sizes) | Every lever in the 90-day plan is sized off assumptions | Hours, in Stripe + PostHog |
| 2 | Is the payment-activation bug live in production? | Users who **decided to pay** may be failing to pay right now | One test transaction |
| 3 | Real LLM/infra cost per unit and its trend | Determines gross margin and whether growth is affordable | Days |
| 4 | Formaviva's real one-page P&L and blended take rate | Determines whether "cap it" or "wind it down" is honest | Days |
| 5 | Personal health baseline | No monitor on the most critical dependency in the system | One appointment |
| 6 | Personal runway independent of both businesses | Determines whether decisions are made from strength or fear | An afternoon |

**Items 1, 2, 5 and 6 are all resolvable inside two weeks and together remove
most of the fog.** That is the highest return available anywhere in this repo,
and none of it is engineering.

---

## The honest summary

The businesses are not failing. Nightwatch is profitable with a real moat and a
correct strategy. Formaviva is a genuine asset that has never had a revenue
model. What is failing is **the allocation**: one person is the growth function,
the product function, the strategy function, the escalation point, and the
second company — while operating on estimated numbers and without a health
baseline.

That is not a motivation problem or a market problem. It is a **capacity
problem**, and capacity problems are solved by subtraction and delegation, never
by effort.
