# Formaviva — The Honest Position

_This is the hardest document in the repo, because Formaviva is the project that
is loved. The temptation is to be either brutal ("shut it down, the math
doesn't work") or sentimental ("keep pushing, it'll turn"). Both are wrong, and
both are expensive._

---

## The two ledgers

Formaviva is currently being measured on one ledger and valued on another, and
that mismatch is the entire source of the guilt.

| | **Business ledger** | **Life ledger** |
|---|---|---|
| Question | Does it make money? | Does it make the life better? |
| Answer today | **No, and structurally not** — `02-why-not-profitable.md` proves the commission model cannot close, and there is no MRR live | **Yes** — it is the loved work, creative renewal, identity, standing in a scene that matters |
| Verdict | Failing | Succeeding |

**Both answers are true simultaneously.** The mistake is letting the business
ledger's verdict determine the project's right to exist, and then feeling
personal failure every time the business ledger reports what it was always going
to report.

**Formaviva does not owe anyone profitability to justify its existence. It owes
a cap.** A capped, loved, unprofitable project is a legitimate and healthy thing
for a founder to own. An uncapped, loved, unprofitable project that quietly
consumes engineering time, evenings, and emotional bandwidth during a diligence
quarter is not — that is how the thing that gives energy becomes the thing that
takes it.

---

## What the business analysis actually says

The work in `formaviva-org` is good and its conclusions are sound. Restated
without softening:

1. **Commission-only cannot reach break-even.** At a blended ~5% take, a €10
   digital sale nets ~€0.50 while Braintree takes ~€0.59. **The payment
   processor can earn more per sale than the platform does.** Break-even on
   commission alone needs €40–80K/month of GMV from a deliberately small curated
   catalog.
2. **Membership changes the shape** — ~150 Pro artists + ~500 paying listeners
   covers a ~€4K/month base. Reachable in principle.
3. **The cost base is a much larger company's** — four codebases, three web
   front-ends, an EOL stack (Ruby 2.4 / Rails 5.1 / PG 9.6), manual payouts via
   Retool, and streaming bandwidth that scales with *non-paying* usage.
4. **The recommended path (Option B) needs ~12 months** of consolidation,
   modernization, subscription build, and a growth engine.

### The thing the analysis does not say

`06-pivot-options.md` scores Option B on revenue potential, defensibility, asset
fit, execution cost, and team fit. **It does not score it on founder capacity —
because it cannot see Nightwatch.**

From the personal vantage point, that column is decisive:

> **Option B is the correct strategy and cannot be executed now.**

It requires 12 months of scarce engineering and sustained founder attention,
during the exact quarter when Nightwatch has diligence ahead of a launch, a
$64K→$75K target, and a founder already on the critical path of two of its own
levers. Running both at full intensity means both are run badly, and the one
with 800 paying customers and 11 salaries attached is the one that cannot afford
it.

**Pushing Formaviva now is not commitment. It is the same breadth failure that
both repos already diagnosed, wearing the costume of passion.**

---

## The recommendation: cap it, don't kill it, don't push it

A third option, absent from `06-pivot-options.md` because that document was
written from the company's perspective rather than the operator's:

> ### Option E — Protected Asset Mode
> **Keep Formaviva alive, loved, secure, and small. Cap the money, cap the
> hours, freeze the ambition. Decide its real future when Nightwatch's endgame
> resolves.**

This is not Option D (harvest as media) and it is not slow-motion shutdown. It
is a **deliberate holding pattern with a defined end**, which is precisely what
distinguishes it from the status quo — because the status quo is already a
holding pattern, just an undeclared one that generates guilt instead of clarity.

### What Protected Asset Mode means concretely

**Money cap.** A fixed monthly euro figure, decided once, treated as a
subscription to something valued — the way one would treat a studio rental or a
sailing club. Inside the cap, no guilt. Outside the cap, no.

**Time cap.** One bounded slot per week ([`04`](04-time-and-attention.md)). Not
evenings, not weekends bleeding, not during Nightwatch deep-work blocks.
Approvals, A&R, and curation all live inside the slot.

**Engineering: security and continuity only.**
- ✅ The EOL stack upgrade path (Ruby 2.4 / Rails 5.1 / PG 9.6). **This is not
  optional** — it is a live security exposure on a platform holding other
  people's money and personal data. It is the one genuinely urgent engineering
  item.
- ✅ Keeping the lights on: backups, uptime, payment integrity.
- ❌ Feature work.
- ❌ The Next.js parity push.
- ❌ Anything on the Solid front-end — that decision is already made
  (`07-execution-roadmap.md`: one stack, Ember read-only, Solid dropped).

**Reduce the operational surface.** Not because these are bad, but because each
is a small recurring tax on a capped budget:
- Consider pausing or simplifying **physical merch** — explicitly low-margin,
  high-touch, with shipping/VAT support overhead disproportionate to the
  commission earned.
- Move payouts toward the least manual option available within the cap — manual
  Retool settlement is both a time cost and a compliance surface (the platform
  holds sellers' funds in a single merchant account).
- Slow the A&R intake if approvals are a bottleneck; a smaller, well-served
  roster beats a growing, badly-served one.

**Keep the part that is actually loved and actually cheap.** The curation,
editorial, and radio/mix show. This is the highest joy-per-hour component, it
requires no engineering, it is the documented top-of-funnel for any future
revival (Option D as the funnel for Option B), and it keeps the brand and the
relationships alive. **If everything else is capped, this is what survives — and
it should.**

**Use the AI skills that already exist.** `formaviva-org/.claude/skills/` already
ships `ar-triage`, `release-copy`, `scene-content`, `scene-radar`, and
`support-copilot` — written precisely for this: _"AI's job here is to make the
small team punch far above its weight."_ In Protected Asset Mode they become
essential rather than nice-to-have, because they let one bounded slot per week
produce what previously took several.

**Raise the take rate quietly, without breaking trust.** Grandfather existing
deals. Set new artists at the standard 10%. `06-pivot-options.md` already lists
this as an Option-A tactic worth doing regardless of strategy. It does not
require a pivot, and it slightly narrows the gap.

---

## The decision date and the criteria

The cap is worthless without a date. Undated caps become slow starvation, which
is the outcome to avoid.

> **Decision date: when the Nightwatch endgame resolves** (diligence/launch
> outcome known) **or 12 months from now, whichever comes first.**

At that date, choose explicitly — in writing, with the reasoning recorded:

| If… | Then |
|---|---|
| Nightwatch outcome creates real resources (money and/or freed time) | **Fund Option B properly** — a real team, a real 12 months, membership shipped. This is the version where Formaviva gets an honest chance instead of scraps |
| Nightwatch continues to demand everything | **Option D** — keep the curatorial brand, radio, and editorial as a media/community property with a tiny cost base; wind the marketplace down gracefully |
| Neither is sustainable | **Hand it over** — to a co-founder, the community, or a scene-aligned owner. A curated brand with real artist relationships is worth more transferred than abandoned |

**Never: quiet attrition.** Letting it decay by neglect is the only genuinely bad
outcome — it loses the asset, damages the relationships, and produces guilt
without producing a decision.

---

## Reframes worth internalizing

**"Unprofitable" is not the same as "failed."** Formaviva was never given a
revenue model — web subscriptions were never built, the free quota exists in code
but is disabled, the take rate was discounted to near zero as a marketing
promise. It is not that the business model was tried and failed; **it is that
there was never a business model to try.** That is a materially different fact,
and it means the Option B question is still genuinely open — just not open now.

**Optimizing it for profit might destroy what makes it worth keeping.** The
curation, the scene relationships, the "no charge for creators" ethos — these are
the things that make it loved *and* the things that make it unprofitable.
Aggressive monetization would likely produce a mediocre business and a lost
identity. Protected Asset Mode preserves the option to monetize later, with
resources, without spending the asset now.

**The scene is the moat and it does not depreciate quickly.** Trust with artists,
taste, and standing take years to build and do not evaporate over a capped year.
This is the strongest argument that waiting is genuinely cheap here — unlike
Nightwatch, where the AI-search window is time-sensitive.

**Capping it is an act of respect, not abandonment.** The alternative — pushing it
in the margins of a diligence quarter — is what actually risks it, because
half-executed pivots on EOL stacks fail and take the brand's credibility with
them.

---

## What this buys

| Before | After |
|---|---|
| Unbounded time, ad hoc, evenings and weekends | One slot per week |
| Unbounded and unmeasured spend | A fixed monthly figure, guilt-free inside it |
| Guilt every time it is looked at | A policy, and a date |
| Engineering split three ways with no owner | Security-only, defined, finite |
| Judged as a failing business | Held as a protected asset with an open option |
| Decision deferred indefinitely | Decision dated and criteria written |

The energy recovered here does not primarily come from the hours. It comes from
**removing an open, undecidable question** that currently reasserts itself every
time the project is looked at. Deciding to cap it is cheaper than continuing to
decide it every week.
