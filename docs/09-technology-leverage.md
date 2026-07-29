# Technology Leverage — What Is Actually Possible Today, and What Is Reasonable

_The brief was "utilize technology for optimal experience in life, business, and
free time." This document separates the three questions that usually get
conflated: what is possible, what is reasonable **for this person, this
quarter**, and what is a trap._

---

## The governing constraint

**The binding constraint is founder attention, not capability.** `formaviva-org`
states it exactly right:

> _"Formaviva's binding constraint is people-hours, not ideas… AI's job here is
> to make the small team punch far above its weight."_ (`11-ai-strategy.md`)

Which produces the rule that governs everything below:

> ### ⚠️ Adopt, don't build.
> **Every hour spent building personal tooling is an hour not spent on the
> bottleneck — and a half-built personal system becomes a third venture.**

Given a documented history of three web front-ends and four codebases, this is
not a hypothetical risk. It is the most likely way this document gets misused.
If a "personal productivity system" project ever appears on the roadmap, that is
the failure mode arriving, and Gate 3 applies: what is being removed to make room
for it?

**Test for anything in this document:** does it save more hours per month than
it costs to set up and maintain, within 30 days? If not, skip it. If unsure,
skip it.

---

## Tier 1 — Do now (high leverage, near-zero build)

### 1. Use the skills that already exist

Both repos already ship working Claude skills. This is done work sitting unused:

| Repo | Skills |
|---|---|
| `nightwatch-org` | `migration-upsell`, `cro-experiment`, `nightwatch-cold-outreach`, `churn-save`, `ppc-b2b` |
| `formaviva-org` | `ar-triage`, `release-copy`, `scene-content`, `scene-radar`, `support-copilot` |

`migration-upsell` alone encodes Lever 1 — the single highest-certainty MRR in
the 90-day plan. `ar-triage` and `scene-content` are what make Formaviva's
one-slot-per-week cap actually workable.

**Adjustment:** the tracker lists "Enable marketplace plugins" as a 🔴 open
blocker. Close it. Then make skill usage the default for the recurring work
rather than an occasional experiment.

### 2. Replace continuous competitive monitoring with a scheduled digest

The single highest-value AI application for the stated energy drains. Instead of
ambient monitoring of Peec, Semrush, Ahrefs, and the AI-visibility category, an
agent produces **one monthly digest**, and the founder reads a document instead
of performing surveillance. `formaviva-org` already models this with
`scene-radar`; Nightwatch needs the equivalent.

**Effect:** converts an unbounded anxiety loop into a 30-minute scheduled read —
without losing any signal that would change a locked decision
([`05`](05-decision-framework.md)).

### 3. Automate the weekly numbers, stop assembling them by hand

`MRR-EXECUTION-TRACKER.md` is filled in manually every Monday. That is exactly
the work that should be generated: pull Stripe and PostHog, produce the actuals
row and the leading indicators, flag anything off-trend. The founder reviews and
decides; the assembly is not founder work.

**Effect:** makes the Monday review reliable rather than dependent on energy —
and manual dashboards are always the first thing dropped in a bad week, which is
precisely the week the numbers matter most.

### 4. Draft-first support and outreach

Support replies, migration emails, demo follow-ups, objection responses — all
have canonical source docs and skills already written for them
(`support-copilot`, `objection-handling.md`, `sales-playbook.md`). AI drafts, a
human edits and sends. Never auto-send anything customer-facing.

### 5. Notification and alert routing

The least glamorous and among the highest-value items in this repo. Covered in
[`03`](03-energy-and-health.md) and [`06`](06-nightwatch-adjustments.md):
on-call rotation, founder off default alert paths, OS-level after-hours silence.
This is technology used to *remove* input, which is the form of leverage most
often overlooked.

---

## Tier 2 — Worth doing this quarter (modest setup)

### 6. A cost/reliability dashboard

The metrics from [`06`](06-nightwatch-adjustments.md) — cost per tracked
keyword, cost per AI prompt by model, blended gross margin, pager events per
week, Sidekiq backlog p95 — on one page, updated weekly. Owned by the named
engineer, not the founder.

**Why it matters more than it looks:** most of the anxiety around
"processing/scalability problems" is about not knowing the trend, not about the
incidents. A visible falling line resolves it.

### 7. AI cost controls in the product, not in effort

Already agreed and already specified: LLM routing (cheap models for routine
checks, premium for the ones that matter), 24-hour dedupe caching, batch
processing, and soft caps with overage billing. `CONCLUSIONS.md` §10 assumed a
40% AI-cost reduction **with no plan** — this is the plan, and it is a product
and pricing decision rather than an engineering-heroics one.

### 8. A single personal capture inbox

One place where every thought, task, and idea lands, from any device, cleared in
the Monday review. Whatever is already used — notes app, task app, a text file.
**No migration project. No new system.** The value is in having exactly one
inbox, not in which one it is.

### 9. Personal metrics, minimally

The five-line weekly dashboard from [`03`](03-energy-and-health.md). A wearable
is optional and genuinely useful for sleep and resting-heart-rate trends — but
only if it is glanced at weekly, not analyzed daily. **A tracker that generates
anxiety about the metric it tracks has inverted its purpose**, which is a real
failure mode for exactly this personality type.

---

## Tier 3 — Possible, but not now

Real and useful; wrong quarter. Listed so they can be recognized as deliberate
deferrals rather than oversights.

| Thing | Why not now |
|---|---|
| Custom internal AI agents / bespoke automation platform | This is building, not adopting. A third venture in disguise |
| Home automation, quantified-self depth, elaborate personal dashboards | Fun, genuinely enjoyable to build, and precisely the craft-over-focus trap ranked last in the decision hierarchy |
| Migrating tools (notes, tasks, calendar) to something better | Migration cost is certain; benefit is marginal. Use what exists |
| A personal knowledge-management overhaul | This repo **is** the knowledge base. Do not build a system around the system |
| AI-in-product features at Formaviva | Excellent ideas in `11-ai-strategy.md`; blocked by the cap, by design |

---

## Technology in free time

The brief included free time, and it deserves an explicit answer, because the
default here is that technology colonizes it.

**Use technology to protect free time, not to optimize it.**

- **The best tech decision for free time is usually less of it.** Phone out of
  the bedroom, notifications off at a set hour, no work apps on the personal
  device, weekends without a laptop.
- **Automate the admin, not the enjoyment.** Groceries, bills, scheduling,
  travel logistics — worth automating. Music listening, cooking, exercise,
  friendship — not things to optimize. Optimizing enjoyment is how a hobby
  becomes a project, and this is the exact mechanism by which Formaviva
  drifted from joy toward obligation.
- **Formaviva is the free-time asset that must not become a job.** Protecting
  that is the entire logic of the cap in [`07`](07-formaviva-adjustments.md).
- **Keep at least one analogue thing** — an activity with no screen, no metric,
  and no output. Walking, cooking, records, sport, whatever it is. It is the
  only reliable off-switch for a mind that is otherwise always in a system.

---

## What "possible today" honestly means

Setting expectations, because AI capability discourse is noisy:

**Genuinely reliable today:**
- Drafting, summarizing, and restructuring text at professional quality
- Research and monitoring digests over public sources
- Code assistance, review, and mechanical refactors
- Data pulls, analysis, and recurring report generation
- Triage and classification with a human decision at the end

**Not reliable enough to be unsupervised:**
- Anything sent to a customer without a human read
- Financial or legal conclusions taken as fact
- Strategic judgment — it can structure the thinking, it cannot own the call
- Anything where a confident error is expensive to unwind

**The practical rule:** AI drafts and monitors; humans decide and send. Both
repos' skills are already written to that contract, and that contract is why they
are safe to rely on.

---

## The one-line version

> **Adopt what exists, automate the assembly of numbers and the monitoring of
> competitors, route alerts away from yourself, and refuse to build a personal
> system. The leverage is in removing inputs, not in adding tools.**
