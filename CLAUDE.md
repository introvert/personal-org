# CLAUDE.md — Agent Operating Guide for `personal-org`

This repository is the **personal knowledge base** for the operator of
`nightwatch-org` (B2B SaaS, the engine) and `formaviva-org` (underground
electronic music platform, the loved project). It holds life strategy, health
and energy protocols, decision frameworks, and portfolio-level calls — not
application code and not business strategy.

Read this file first, then [`README.md`](README.md), then
[`docs/00-executive-summary.md`](docs/00-executive-summary.md).

## The mission

**Retain health and energy while running two ventures, and make the highest-level
adjustments deliberately rather than by default.** The core diagnosis: one person
is carrying roughly four companies' worth of operating surface. The remedy is
subtraction — cap Formaviva, de-bottleneck Nightwatch, make invisible costs
visible, protect the floor.

## Source-of-truth map

| Topic | Canonical doc |
|-------|---------------|
| The whole argument | `docs/00-executive-summary.md` |
| Goals, values, decision hierarchy | `docs/01-life-thesis.md` |
| Baseline, energy audit, unknowns | `docs/02-current-state.md` |
| Health & energy protocol | `docs/03-energy-and-health.md` |
| Weekly operating system | `docs/04-time-and-attention.md` |
| How to decide (5 gates, standing decisions) | `docs/05-decision-framework.md` |
| Nightwatch operator-level changes | `docs/06-nightwatch-adjustments.md` |
| Formaviva position (Protected Asset Mode) | `docs/07-formaviva-adjustments.md` |
| Portfolio, financial floor, endgame | `docs/08-portfolio-strategy.md` |
| Tech/AI leverage — and the traps | `docs/09-technology-leverage.md` |
| What to do now | `docs/10-90-day-plan.md` |
| Reviews and drift signals | `docs/11-review-cadence.md` |

**Business facts live in the business repos.** `nightwatch-org` (pricing,
strategy, MRR plan, execution tracker) and `formaviva-org` (pivot options,
financial model, roadmap) are authoritative for their own domains. This repo
cites them; it never restates or overrides them.

## Guardrails (non-negotiable)

- **Do not re-litigate settled business decisions.** Nightwatch v4 pricing,
  "Search Intelligence" positioning, Peec-as-tailwind, Formaviva's one-web-stack
  call — all closed. Full list in `docs/05-decision-framework.md`. If one comes
  up, answer "already decided" and cite the doc.
- **Health content is an operating protocol, never medical advice.** Anything
  touching symptoms, diagnosis, dosage, or treatment routes to a doctor. Do not
  interpret lab results or recommend supplements.
- **Cite, don't invent.** Every claim about either business must trace to a doc
  in the relevant repo. No fabricated figures. Where a number is an assumption
  (most Nightwatch baseline metrics; all Formaviva financials), say so.
- **Subtraction bias.** Default to recommending removal, delegation, or a cap
  over addition. If a proposal adds surface, name what it removes
  (`docs/05-decision-framework.md` Gate 3).
- **Never propose that this repo grow a tooling layer.** No apps, dashboards,
  automations, or systems built around these documents. Adopt, don't build
  (`docs/09-technology-leverage.md`).
- **Formaviva is capped, not killed and not pushed.** Do not draft Option B
  execution work; do not propose winding it down. The cap and the decision date
  are the position.

## How to execute a task well here

1. Identify which document the task maps to; read it before drafting anything.
2. Read the relevant canonical doc in `nightwatch-org` or `formaviva-org` if the
   task touches a business fact.
3. Run non-trivial proposals through the five gates in
   `docs/05-decision-framework.md` — especially Gate 4 ("does this land on the
   founder's queue?") and Gate 5 ("what kills it, and by when?").
4. Produce concrete output — a decision, a cap, a delegation, a deleted item —
   not generic life advice.
5. Keep it short. This repo's value is that it is small enough to actually re-read.

## Repo hygiene

- Keep the doc set at roughly its current size. Adding a document should usually
  mean merging or deleting another — the repo practices what it recommends.
- Update docs with a date when an assumption is tested or a decision changes.
- Prose over frameworks-for-their-own-sake; every section should change a
  behaviour, not just describe one.
