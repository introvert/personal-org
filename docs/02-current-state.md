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
| Team | **~3 people** (support, development, infra) — see cost base below. `team.md` still lists ~11 from an **Apr 2025 snapshot and is stale** | Founder, 2026-07 |
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

## The real cost base (founder figures, 2026-07)

> ⚠️ Supersedes `nightwatch-org/docs/01-company/team.md`, which is an April 2025
> snapshot listing ~11 people. **That doc should be updated in its own repo.**
> Two figures below were ambiguous when given and are marked; the revenue number
> is still unconfirmed (P0 #2).

### The monthly numbers

| Line | USD/month | Note |
|---|---|---|
| Customer support (1 person) | **$2,300** | |
| Development | **$2,000** | |
| Infrastructure / DevOps person | **$2,500** | |
| **People subtotal** | **$6,800** | ~3 people, ~$27K/yr average |
| Servers & processing infrastructure | **$5,000** | of which ~$2,000 is processing/SERP fetching ⚠️ |
| Other services | **$1,000–2,000** | take $1,500 midpoint |
| **Infrastructure subtotal** | **$6,500** | |
| **TOTAL OPEX** | **≈ $13,300/mo** | ≈ **$160K/year** |

⚠️ **Sensitivity.** If the $2,000 processing figure is *additional* to the $5,000
rather than inside it, infrastructure is $7,000 and total opex is **$15,300/mo**
(≈$184K/yr). Materially different for planning, not decision-changing at this
revenue. Confirm which reading is right.

### What it implies

Revenue "slipped slightly" from $64K MRR. Modelled across a range, because the
actual figure is still one of the P0 items:

| MRR | Annual revenue | Opex | **Monthly surplus** | Operating margin |
|---|---|---|---|---|
| $64,000 | $768K | $13,300 | **$50,700** | 79% |
| $60,000 | $720K | $13,300 | **$46,700** | **78%** |
| $56,000 | $672K | $13,300 | **$42,700** | 76% |

- **Gross margin ≈ 89%** (revenue less infrastructure and services). Well above
  the ~68% blended target assumed in `CONCLUSIONS.md` §8.
- **Operating margin ≈ 78%.** This is an unusually profitable small software
  business.
- **Roughly $560K/year of operating surplus** at $60K MRR.

### The three structural facts this reveals

**1. Infrastructure now costs about the same as the entire payroll.**
$6,500 infra vs $6,800 people — infrastructure is **49% of opex**. In typical
SaaS, payroll is 60–70% of opex; here it is 51%. Not because infrastructure grew
unusually, but because **the team shrank and the infrastructure didn't.** The
system still serves millions of keywords daily across 107K locations and 5 LLM
providers, whatever the headcount is.

> **Consequence: infrastructure cost reduction is now literally equivalent to
> hiring.** A 30% cut is ~$1,950/month — the cost of a whole additional engineer
> at current rates. And the levers are already documented and unowned (LLM
> routing, dedupe caching, batching, ClickHouse optimization).

**2. Support costs more than development.** $2,300 vs $2,000. Support load
scales with **customer count**, not revenue — so a long tail of small accounts is
now the single largest people cost in the company. **This is direct evidence for
the upmarket concentration thesis** in [`12`](12-long-term-and-repositioning.md),
no longer just an argument from theory.

**3. Money was never the constraint on hiring.** At ~$46,700/month of surplus, a
growth owner at $3,000–5,000/month costs **6–11% of surplus**, and needs to
generate ~$4–5K MRR to be free. **Lever 1 alone targets +$4,500 in work that is
already scoped.** The hire is self-funding out of a campaign that is already
planned.

### The risk that replaced the money risk

Financially this business is robust. **Operationally it is now extremely
fragile:** roughly three people carrying seven-plus services — Rails, two Go
services, Ember, React, ClickHouse, Kafka, Sidekiq, Kubernetes — across 107,296
locations and five LLM providers.

**Bus factor is 1 on essentially everything.** That is the dominant risk now,
and it is also precisely what diligence discounts hardest (key-person
dependency). The financial cushion is large enough to fix it; the fix is owners
and documented redundancy, not more money.

### Revenue direction matters more than revenue level

At 78% operating margin, a few thousand dollars of MRR decline is not
existential — each $1K lost is ~2% of surplus. **But direction is the thing
being bought.** Declining MRR going into diligence is the worst single optic in
a data room, and it re-ranks the plan: **retention and expansion now outrank new
logo acquisition.** Lever 7 (churn-save) and Lever 1 (migration/upsell) move up;
they are also the two cheapest levers to run.

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

## The unknowns register

_Updated 2026-07. Ranked by how much each is currently distorting decisions.
This table is the honest statement of how much of this repo rests on estimates._

### Resolved

| Unknown | Status |
|---|---|
| Team size and people cost | ✅ ~3 people, $6,800/mo |
| Total cost base | ✅ ~$13,300/mo (one ambiguity remains, below) |
| Gross and operating margin | ✅ ~89% / ~78% at $60K MRR |
| Revenue per employee | ✅ ~$240K ARR/head |

### Still open — ranked

| # | Unknown | Why it matters | Cost |
|---|---|---|---|
| 1 | **Why did revenue slip?** Churn, contraction, or fewer new? | **The most decision-relevant unknown right now.** Each cause implies a completely different response, and I have no data to distinguish them | Hours |
| 2 | **Current MRR, exactly** | Everything downstream — margin, surplus, hire affordability, diligence optics — is modelled across $56–64K | Minutes |
| 3 | Baseline cohort data (customers, ARPA, churn, conversion, legacy sizes) | **Lever 1's +$4,500 is sized off "~550 customers below €99."** If that number is wrong, the highest-certainty lever in the plan is mis-sized | Hours |
| 4 | Is the payment-activation bug live? | Binary, and money may be leaking now | 1 hour |
| 5 | **What "diligence ahead of a launch" actually is** — acquisition, fundraise, or something else | This repo has assumed acquisition-flavoured throughout. If it is a raise, the endgame document, the growth-vs-margin trade-off, and the hiring stance all change | A conversation |
| 6 | Is the $2,000 processing cost inside or on top of the $5,000? | $24K/year | Minutes |
| 7 | Formaviva's real one-page P&L | The cap was recommended without knowing what it currently costs | Days |
| 8 | **Who else has a stake in Formaviva?** The docs say "founders," plural | The handover branch is unwritable without this | A conversation |
| 9 | Employment status of dev and infra (FTE, contractor, part-time?) | Materially changes what can be delegated and how fast | Known to founder |
| 10 | Personal health baseline | No monitor on the most critical dependency | One appointment |
| 11 | Personal runway, burn, exposure, "enough" number | Determines whether decisions come from strength or fear | An afternoon |
| 12 | Corporate/tax structure, share structure, obligations | Cannot plan an endgame without it | An advisor conversation |

### Assumptions this repo makes that were never verified

Stated plainly, because an unmarked assumption behaves like a fact:

- That competitive monitoring is **continuous** and anxiety-producing — inferred
  from how the problem was described, never measured.
- That the founder's week is overloaded in the specific shape described — **no
  actual hours audit has been run.** The energy audit in this document is
  reasoning from documents, not from data.
- That the sub-€99 base is a support burden — plausible given support > dev
  cost, but **no ticket data was examined.**
- That the data/API opportunity is real — desk reasoning only. That is precisely
  what the ten conversations are for.

### The structural gap

**No customer voice anywhere in this analysis.** Nothing here draws on why
customers actually churn, what they would pay more for, or what the sub-€99 base
wants. The upmarket thesis, Lever 1's sizing, and the churn response all
ultimately depend on it, and all three are currently built from internal
documents alone.

> **Everything in this repo was derived from documents written inside these two
> organizations. That is a closed loop — self-consistent, and capable of sharing
> a blind spot.** The inputs that would break the loop are external: customers, a
> peer founder or advisor, the actual questions the counterparty asks in
> diligence, and a doctor.

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
