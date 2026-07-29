# The 90-Day Plan — What To Actually Do

_Everything else in this repo is analysis. This is the executable part._

**Design principle: this plan adds almost nothing. It removes, delegates, and
measures.** It is built to run *underneath* the Nightwatch 90-day MRR sprint
without competing with it — because a personal plan that competes with the
business plan will lose, and should.

---

## The four outcomes

By day 90:

| # | Outcome | Measure |
|---|---|---|
| **O1** | **The floor is real** | Sleep anchor ≥5 nights/week; medical baseline taken; one off day per week held; after-hours alerts at zero by default |
| **O2** | **The numbers are known** | Nightwatch baseline confirmed from Stripe/PostHog; Formaviva one-page P&L exists; personal runway computed |
| **O3** | **The founder is off two of three critical paths** | A named non-founder growth owner; Lever 1 owned by CS; demos remain the only personally-owned lever |
| **O4** | **Formaviva is capped, not carried** | Written cap (money + hours), security-only engineering, decision date set |

Four outcomes. Not fourteen. This is Deliberate Smallness applied to the plan
about Deliberate Smallness.

---

## Weeks 1–2 — Close the open loops

The cheapest, highest-return fortnight available. Almost none of it is new work;
most of it is *finishing things that are already open*.

### Business
- [ ] **Drive a real card through the payment flow.** Is the payment-activation
      bug live in production? This is Day 1 in the MRR plan and still marked
      unverified in the tracker. Users who already decided to pay may be failing
      to pay right now.
- [ ] **Confirm the baseline from Stripe + PostHog** — customers, ARPA, churn,
      trial conversion, legacy cohort sizes. Fill the tracker's baseline table
      and freeze it. Every lever is currently sized on assumptions.
- [ ] **Close the third 🔴 blocker** — enable the marketplace plugins.
- [ ] **Reconcile the revenue narrative** — one number, used everywhere. The
      €1.5M ARR / $64K MRR discrepancy is resolved in one doc and contradicted in
      several; before diligence, that is a credibility risk as well as a source
      of internal confusion.

### Personal
- [ ] **Book the physical and bloodwork.** Booking counts; the appointment can be
      later.
- [ ] **Set the wake anchor.** One time, ≥5 days/week.
- [ ] **Turn off after-hours notifications** at the OS level. Tonight.
- [ ] **Compute personal runway** — one afternoon, one page.

### Formaviva
- [ ] **Write the cap.** A number per month, a slot per week, security-only
      engineering. One paragraph is enough — but write it down, because an
      unwritten cap is not a cap.

**Week-2 checkpoint:** three 🔴 blockers closed, baseline frozen, physical
booked, cap written.

---

## Weeks 3–6 — Delegate and structure

Now the load actually starts coming down.

### Business
- [ ] **Name the growth owner.** Internal promotion, fractional hire, or start
      the search — but name someone this month. Do not defer to Phase 3; the
      risk table already flags founder bottleneck as high-probability *now*.
- [ ] **Hand Lever 1 to CS.** Cohorts, sequence, and calls run by CS using the
      `migration-upsell` skill. Founder takes only the largest accounts.
- [ ] **Set up the on-call rotation** and route Sentry/uptime/backlog alerts away
      from the founder by default. Define what justifies waking a human.
- [ ] **Name the unit-economics owner** and stand up the weekly cost/reliability
      page: cost per keyword, cost per prompt by model, gross margin, pager
      events, Sidekiq p95.
- [ ] **Batch the demos** into two afternoon blocks.

### Personal
- [ ] **Take the physical.**
- [ ] **Add morning light + a daily walk.** Ten minutes outside within an hour of
      waking.
- [ ] **Put two deep-work blocks on the calendar** and defend them.
- [ ] **Take one full off day** — no Slack, no Sentry, no strategy reading.
- [ ] **Start the Monday review and Friday close.** 30 and 15 minutes.

### Formaviva
- [ ] **Move everything into the weekly slot.** Approvals, A&R, curation.
- [ ] **Start the EOL stack upgrade path** — the one genuinely urgent engineering
      item. Staged and incremental, inside the cap.
- [ ] **Switch on the existing skills** for A&R triage and content, so the slot
      produces more than the hours suggest.

**Week-6 checkpoint:** growth owner named; Lever 1 off the founder's desk;
alerts routed away; cost page live; the week has a shape.

---

## Weeks 7–12 — Consolidate and decide

### Business
- [ ] **Founder footprint check** — is the only personally-owned lever now
      demos? If not, what is still attached and why?
- [ ] **Answer the 3× capacity question** in writing, once. Where does the stack
      break, what does it cost to fix. Closes a long-carried open loop and is a
      diligence asset regardless.
- [ ] **First monthly competitive review** — one block, one document, then
      nothing until the next one.
- [ ] **Hold the no-new-surface line.** Zero new product surface started this
      quarter.

### Personal
- [ ] **Add strength sessions** to the calendar as recurring meetings. 2–3/week,
      30–45 minutes. Start at a volume that survives a bad week.
- [ ] **Book an actual holiday** with coverage arranged.
- [ ] **Review the five-line dashboard trend.** Energy trending up?

### The one big thing
- [ ] **Write the endgame document** ([`08`](08-portfolio-strategy.md)) in a
      dedicated Owner block. What outcome are you actually optimizing for; the
      walk-away number and terms; what you will not trade; life after each
      scenario; what each scenario means for Formaviva.

**This is the highest-value single item in the entire repo.** Diligence is ahead
of a launch. Write the answer before the process makes it urgent.

**Day-90 checkpoint:** run the four outcomes. Anything red is a capacity signal,
not a discipline failure — and the response is subtraction, per
[`05`](05-decision-framework.md).

---

## What this plan deliberately does NOT do

Mirroring the discipline of `MRR-SCALING-PLAN.md`, whose "not doing" list is its
most valuable section:

- ❌ **No new personal productivity system.** No app migrations, no custom
      tooling, no quantified-self project. Adopt, don't build.
- ❌ **No Formaviva pivot execution.** Option B is correct and is not this
      quarter's work. The cap is the decision.
- ❌ **No new Nightwatch product surface.** The quarter is conversion and
      expansion of demand that already exists.
- ❌ **No re-litigating settled decisions** — pricing, positioning, the tailwind
      strategy, one web stack. All closed.
- ❌ **No ambitious health program.** Five items over three months, at a volume
      that survives a bad week.
- ❌ **No fourteen goals.** Four outcomes.

---

## The tracker

Copy into a weekly note. Five minutes in the Monday review.

| Week | Sleep anchor (of 7) | Movement | Off day | Energy 1–5 | Founder-owned levers | 🔴 open loops | Formaviva hrs |
|---|---|---|---|---|---|---|---|
| 1 | | | | | 2+ | 3 | |
| 2 | | | | | | | |
| … | | | | | | | |
| 12 | ≥5 | ≥3 | ✅ | ≥3 ↑ | **1** | **0** | ≤ cap |

**Read the right-hand columns as the real scoreboard.** MRR is already tracked
in `MRR-EXECUTION-TRACKER.md` and it measures the business. These columns measure
whether the *operator* changed — and if the operator does not change, next
quarter is this quarter with less energy in reserve.

---

## If the plan slips

It will slip. That is expected and pre-decided so it does not turn into guilt:

1. **Protect O1 (the floor) above all others.** If only one outcome survives,
   make it that one.
2. **Cut from the business outcomes before the personal ones.** This inverts the
   current default, which is exactly why it has to be written down.
3. **Three consecutive weeks of energy ≤2 triggers subtraction, not effort** —
   Formaviva pauses fully, Nightwatch drops to essential operations. Pre-decided
   in [`08`](08-portfolio-strategy.md) precisely because good judgment is
   unavailable at the moment it is needed.
4. **A missed week is a missed week.** Resume on Monday. The plan is designed to
   survive bad weeks; that is why it is short.
