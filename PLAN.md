# THE PLAN — Everything, Ranked

_One page. The whole repo reduced to an ordered list. If you read nothing else,
read this._

**How things were ranked:** value ÷ effort, then dependency (what unblocks other
work), then irreversibility (what gets harder if delayed). Cheap things that
unblock expensive things rank above expensive things with bigger payoffs.

**The standing constraint that governs all of it:** _no new surface for 90 days._
Nothing new starts until the quarter closes. Every item below either removes
work, delegates work, or measures something already happening.

---

## P0 — This week

_Five items. Together they cost about two days and close every open loop in the
system. Four of the five are things already started and never finished._

| # | Do this | Why it's #1-5 | Owner | Effort | Done when |
|---|---|---|---|---|---|
| **1** | **Drive a real card through the trial→paid flow.** Is the payment-activation bug live in production? | Users who **already decided to pay** may be failing to pay right now. It's Day 1 in the MRR plan and still unverified in the tracker. Highest return per minute in either repo — and a credibility hit if it surfaces in diligence | Eng | 1 hour to test, 1–3 days to fix | You've watched a real card activate a real subscription |
| **2** | **Pull the real baseline from Stripe + PostHog.** Customers, ARPA, churn, trial conversion, legacy cohort sizes | Every lever in the 90-day plan is sized on assumptions the tracker marks unconfirmed. **You are currently making every decision on estimates** — that's a permanent background tax and it's hours of work, not a project | Founder + Stanko | Hours | Tracker baseline table filled and frozen |
| **3** | **Turn off after-hours notifications. Book the physical.** | Zero cost, tonight. The most critical dependency in the system has no monitor and no baseline. Booking counts — the appointment can be later | You | 20 minutes | Notifications off at OS level; appointment in the calendar |
| **4** | **Write the Formaviva cap.** €/month, hours/week, security-only engineering, decision date | One paragraph converts a permanent open question into a policy. The energy recovered isn't the hours — it's no longer re-deciding it every week | You | 30 minutes | It's written down. An unwritten cap is not a cap |
| **5** | **Enable the marketplace plugins.** | The third 🔴 blocker. Blocks the execution horsepower the whole plan assumes | You | One decision | Done |

> **Items 1, 2 and 5 are literally the three 🔴 open items sitting in
> `MRR-EXECUTION-TRACKER.md`.** They've been open long enough to be carried as
> background load. Closing them is the cheapest week available.

---

## P1 — Weeks 2–6: get off the critical path

_This is the only permanent fix for the energy problem. Everything in P0 is
hygiene; this is the actual change._

| # | Do this | Why it ranks here | Owner | Done when |
|---|---|---|---|---|
| **6** | **Name a growth owner who is not you.** Promote Izabela, hire fractional 2 days/week, or start the search — but name someone this month. **One senior owner with agent leverage, not a growth team** | The MRR plan puts Levers 1 **and** 5 on you, plus marketing, product, positioning and diligence. That's a single-server queue, and it's the constraint on the quarter. Your own risk table flags founder bottleneck as *high probability* and says Phase 2, not Phase 3. **AI does not remove this item** — it produces artifacts, not accountability, and artifacts flow into your approval queue ([`docs/09`](docs/09-technology-leverage.md)) | You → them | A name exists and owns a number |
| **7** | **Hand Lever 1 to CS. Run Lever 7 (churn-save) alongside it** | **Revenue slipped — direction now matters more than level.** Declining MRR is the worst optic in a data room, and these are the two cheapest levers you have. Lever 1 is +$4,500 at zero CAC and mostly systematic; `migration-upsell` and `churn-save` already encode both. Founder involvement scales with account size only | CS | Sequence sent without you writing it; save-flow live |
| **8** | **On-call rotation. Route Sentry/uptime/backlog alerts away from you by default** | Both a health intervention and a delegation forcing-function — engineers who can't escalate to you by default start owning outcomes | Rok + Eng | You are not a default recipient of anything |
| **9** | **Name a unit-economics owner. Stand up the weekly cost page:** cost/keyword, cost/prompt by model, gross margin, pager events, Sidekiq p95. **Target: −30% infrastructure in 6 months** | **Infrastructure is now ~49% of opex and roughly equal to total payroll** ($6.5K vs $6.8K) — the team shrank, the infrastructure didn't. A 30% cut is ~$1,950/mo, **the cost of a whole additional engineer.** Levers already documented and unowned: LLM routing, dedupe caching, batching, ClickHouse tuning | One engineer | One page weekly, not by you; a dated reduction target |
| **10** | **Protect the Citation Intelligence track.** Own owner, own timeline, parallel to the quarter | `CONCLUSIONS.md`: *"if I had to pick one thing… Citation Intelligence must ship well in 3 months."* Your job is **protection, not execution** — don't let the quarter absorb it, don't let it absorb the quarter | Eng lead | It has an owner who isn't you and a dated plan |
| **11** | **Batch demos into two afternoon blocks. No meetings before midday** | Keeps the one lever worth keeping personally (25–30% close rate) without letting it destroy five mornings | You | It's in the calendar and defended |
| **12** | **Start the Formaviva EOL stack upgrade path** (Ruby 2.4 / Rails 5.1 / PG 9.6) | The one genuinely urgent engineering item across both companies — a live security exposure on a platform holding other people's money and data. Staged, incremental, inside the cap | Formaviva eng | A dated staged plan is underway |
| **13** | **Personal: wake anchor, morning light, one off day, Monday review + Friday close** | The floor. Everything above degrades without it, and it's the cheapest item on this page | You | Anchor held ≥5 nights/week for two consecutive weeks |

---

## P2 — Weeks 6–12: decide the future while the quarter runs

_None of this competes with the MRR sprint. Two of them cost one day each and
determine the next five years._

| # | Do this | Why it ranks here | Effort |
|---|---|---|---|
| **14** | **Write the endgame document.** What outcome are you actually optimizing for; walk-away number *and terms*; what you won't trade; life after each scenario; what each means for Formaviva | **The highest-value single item in this repo.** ~30 strategy docs exist and none answers what you want out of this. Diligence is ahead of a launch — decisions made under offer pressure are systematically worse than the same decisions made six months earlier in a quiet room | 1 Owner block |
| **15** | **Run the data/API demand test.** 10 conversations with plausible buyers + one price probe — **include 2–3 AI labs / agent builders** (grounding, retrieval evaluation, provenance) | One day against a possible business-model change — the best expected-value asymmetry available. The AI-grounding buyer is the genuinely uncrowded segment, and it needs no pivot: it's your existing archive sold to a new buyer. **Kill criterion: fewer than 3 of 10 show real willingness to pay → drop it, cost was a day** | 1 day |
| **16** | **Make "concentrate upmarket" explicit as policy.** New acquisition aimed at Agency/Enterprise; declare that customer count may fall while MRR rises | Costs nothing — it's a reframe. But it prevents a *success* (smaller, richer base) from being read as churn. Diligence rewards ARPA and NRR, not logo count | Zero |
| **17** | **Answer the 3× capacity question in writing, once.** Where the stack breaks, what it costs to fix | Closes a loop you've been carrying indefinitely, and it's a diligence asset regardless | Half a day, eng |
| **18** | **First monthly competitive review — then nothing until the next one** | The strategy is locked (Peec = tailwind). Continuous monitoring can't improve a locked decision; it only supplies threat signal | 1 block/month |
| **19** | **Personal: compute runway. Strength sessions on the calendar. Book a holiday** | Runway converts fear into patience, and patience is the highest-value asset in any negotiation | 1 afternoon + calendar |
| **19b** | **Run one function AI-first for 30 days** — the migration campaign. Measure output, rework rate, MRR booked, and **founder review hours** | Tests the AI-first thesis on evidence instead of assertion, on a campaign you're running anyway. **Founder review hours is the decisive metric** — if output rises and your time rises with it, the model is making WIP at the bottleneck. Result rewrites the hiring plan in either direction | Zero marginal |
| **19c** | **Rewrite the Phase-3 hiring plan: owners, not producers.** Kill the Content Lead, defer both AEs, elevate CS to own retention, promote an internal AI/automation owner | ~5 hires (~$700K/yr) → ~1 hire + 2 internal ownership moves. The real AI-first win — without removing the accountability layer that fixes the bottleneck | Half a day |

---

## P3 — After the quarter (months 4–12)

| # | Do this | Trigger |
|---|---|---|
| **20** | **Hire growth and delivery ownership properly** — the permanent version of #6 | Quarter closed; baseline known |
| **21** | **Recovery season.** Not another sprint. Consolidation and rest | Immediately after the 90 days |
| **22** | **Build the data/API line** | Only if #15 passed its gate |
| **23** | **Formaviva decision date** — read the capped year as a live Option D test: *which part still had energy in it?* | 12 months, or when the endgame resolves |
| **24** | **Execute the endgame document** | When the outcome is known |

---

## If you only do five things

1. **Test the payment flow** (#1) — money is possibly leaking right now
2. **Get the real numbers** (#2) — everything else is guesswork until this
3. **Name a growth owner** (#6) — the only permanent fix
4. **Write the endgame document** (#14) — before the process makes it urgent
5. **Hold the wake anchor** (#13) — the floor under all of it

---

## What NOT to do (this is load-bearing)

- ❌ Re-litigate v4 pricing, Search Intelligence positioning, or Peec-as-tailwind. **Settled.**
- ❌ Start any new product surface for 90 days.
- ❌ Execute a Formaviva pivot. The cap **is** the decision — and it's running the Option D test for free.
- ❌ Build the data/API product before #15 passes. Ten conversations first.
- ❌ Chase AI visibility head-on, or add a free tier. Both already killed on unit economics.
- ❌ **Pivot to a different industry.** Every scarce asset stays behind, and it bets everything on distribution — the one capability with a 13-year track record as the weak point. Reopens at the endgame (#14), not before. See [`docs/12`](docs/12-long-term-and-repositioning.md) Part 4.
- ❌ Build a personal productivity system. **Adopt, don't build** — a half-built one becomes a third venture.
- ❌ Add an ambitious health program. Five items over three months, at a volume that survives a bad week.

---

## Order matters — what breaks if you skip ahead

- **Delegating (P1) before the numbers (#2)** hands people a job with no scoreboard. They'll hand it back.
- **The endgame document (#14) before the baseline (#2)** is written on estimates — and it's the one document that must be right.
- **Repositioning (P2/P3) before de-bottlenecking (P1)** puts a new strategy on the same overloaded queue. That is exactly how the last three years produced thirty strategy documents and an unshipped execution list.
- **Anything at all before the floor (#3, #13)** is the pattern that got you here.

---

## The scoreboard

MRR is already tracked in `MRR-EXECUTION-TRACKER.md` — that measures the
business. These measure whether **you** changed, which is what determines
whether next quarter looks like this one:

| Measure | Today | Day 90 |
|---|---|---|
| 🔴 open loops in the tracker | 3 | **0** |
| Levers owned personally by you | 2+ | **1** (demos) |
| Named non-founder growth owner | none | **1** |
| Revenue per employee | ~$240K ARR/head (already strong) | **hold while adding owners** |
| Infrastructure cost | ~$6,500/mo, ~49% of opex, unowned | **owned; −30% target dated** |
| Bus-factor-1 dependencies | ~everything | **documented; ≥1 reduced** |
| Out-of-hours alerts reaching you | default | **0** |
| Cost-per-check visible and owned | no | **yes** |
| Competitive research sessions | continuous | **1/month** |
| Formaviva hours/week | unbounded | **≤ cap** |
| New product surface started | — | **0** |
| Sleep anchor held | unknown | **≥5/7** |
| Endgame document | doesn't exist | **written** |

---

## When it slips

It will. Pre-decided so it doesn't become guilt:

1. **Protect the floor items (#3, #13) above everything else.** If only one thing survives, make it that.
2. **Cut business items before personal ones.** This inverts your current default — which is exactly why it has to be in writing.
3. **Three consecutive weeks at energy ≤2 → subtract, don't push.** Formaviva pauses fully, Nightwatch drops to essential operations.
4. **A missed week is a missed week.** Resume Monday. The plan is short precisely so it survives bad weeks.

---

_Detail behind every item: [`README.md`](README.md) index. Weekly mechanics:
[`docs/04-time-and-attention.md`](docs/04-time-and-attention.md). Why these and
not others: [`docs/05-decision-framework.md`](docs/05-decision-framework.md)._
