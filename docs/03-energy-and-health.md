# Energy & Health — Retaining the Load-Bearing Dependency

> ⚠️ **Not medical advice.** This is an operating protocol, written the way an
> engineering runbook is written. Anything involving symptoms, medication, or a
> diagnosis belongs to a doctor. Item 0 below exists precisely because a
> non-doctor should not be guessing at a baseline.

---

## The framing

Nightwatch runs a 99.98% uptime target, stores raw HTML for every check so any
claim can be verified, and monitors errors through Sentry across every service.
The person running it has **no baseline, no monitor, and no SLA.**

That asymmetry is the finding. Everything below follows from taking the single
most critical dependency in the system as seriously as the ClickHouse cluster.

Three things are being defended here, in order:

1. **Sleep** — the input that everything else degrades without.
2. **Recovery** — the absence of which turns normal load into erosion.
3. **Boundaries** — the mechanism that makes 1 and 2 survivable in a business
   with 24/7 infrastructure and customers in every timezone.

---

## Item 0 — Get a baseline (do this first, this month)

Everything else in this document is guesswork without it.

- **Book a full physical and comprehensive bloodwork.** Founders in their late
  30s/40s routinely skip this for a decade. The point is not to find something
  wrong; it is to have a **trend line** so that the next reading means something.
- **Ask for the standard panel plus the things stress and sedentary work
  actually move:** blood pressure, resting heart rate, lipids, fasting glucose
  / HbA1c, liver and kidney markers, thyroid, vitamin D, B12, ferritin/iron.
- **Mention the actual context to the doctor:** chronic high-responsibility
  work, irregular hours, on-call interruptions, screen-heavy days, sedentary
  posture. Those change what a good doctor looks for.
- **Dentist and eyes** — both drift silently and both are cheap to maintain.
- **If sleep is broken and does not respond to the changes below, ask about a
  sleep assessment.** Untreated sleep disorders are common, invisible from the
  inside, and produce exactly the symptom picture that gets misattributed to
  "startup stress."

**Then repeat annually, on a recurring calendar entry.** A single reading is a
data point; two readings are a monitor.

Alongside it, take one afternoon for the **financial baseline** — personal
runway independent of both businesses (see
[`08-portfolio-strategy.md`](08-portfolio-strategy.md)). Financial fog and
health fog produce the same background load, and both resolve in an afternoon.

---

## The sleep anchor (highest leverage, lowest cost)

One rule, and it is the one that makes the rest possible:

> **A fixed wake time, held ≥5 days a week, including at least one weekend day.**

Wake time is the anchor because it is the only end of sleep that is actually
controllable. Bedtime follows it within a couple of weeks; trying to force
bedtime directly mostly produces lying awake.

Supporting conditions, in rough order of impact:

- **Morning daylight within ~30–60 minutes of waking**, ideally outside, ideally
  10+ minutes. This is the strongest available lever on the sleep/wake rhythm
  and it is free. At Slovenian latitude, winter mornings are dim — go outside
  anyway; overcast daylight still beats indoor lighting by an order of magnitude.
- **Caffeine cutoff ~8–10 hours before bed.** Caffeine's half-life makes an
  afternoon coffee a meaningful sleep-quality tax even when falling asleep feels
  fine.
- **Alcohol is a sleep-quality problem, not a relaxation solution.** It reliably
  fragments the second half of the night. Worth treating as an occasional social
  thing rather than a wind-down tool, precisely because it feels like it works.
- **A hard screen/work boundary before bed.** Not primarily blue light — the
  problem is that a Slack thread or a Sentry alert starts a cognitive process
  that then runs for an hour without permission.
- **Cool, dark, quiet room. Phone charging outside the bedroom.** If the phone
  is the alarm, it will also be the 23:40 incident notification.

**If only one thing in this entire repo gets adopted, make it the wake anchor
plus morning light.** Its downstream effect on decision quality, emotional
tolerance for competitive noise, and willingness to do hard delegation
conversations is larger than any productivity system.

---

## Movement — scheduled as a meeting, never as leftover time

Leftover time does not exist in this operating model. It has not existed for
years, and there is no reason to expect it to appear. So movement is either **on
the calendar with the same status as a customer call**, or it does not happen.

A reasonable, sustainable minimum:

- **2–3 strength sessions/week, 30–45 minutes.** Strength training is the
  highest-value intervention for a desk-based person over 35 — it protects
  posture, back, bone density, metabolic health, and the ability to keep working
  comfortably for another 20 years. It does not require a gym or an hour.
- **Daily walking, ideally after meals and ideally outside.** This doubles as the
  morning-light mechanism and as thinking time. Walking meetings work for
  anything that is not screen-sharing.
- **Something enjoyed for its own sake** — cycling, swimming, hiking, football,
  anything. The adherence problem is the only real problem in exercise; enjoyment
  solves it and discipline does not, over a decade.
- **Deliberate posture and eye breaks** during long screen days. A rough 45/10
  rhythm is enough; the specific numbers matter less than standing up.

**The trap to avoid:** starting an ambitious program in week one, missing three
sessions in week three under an incident, and abandoning it. Start at a volume
that survives a bad week — that is the only volume that compounds.

---

## Boundaries — the specific ones this business needs

Generic advice fails here. These are aimed at the documented realities of
Nightwatch's architecture and Formaviva's ops.

### Alerting and on-call

- **The founder should not be a default alert recipient.** Sentry, uptime, and
  Sidekiq backlog alerts should route to an on-call engineer with a defined
  rotation and a defined escalation path. Escalating to the founder should be a
  deliberate action taken by a person, not a default configuration.
- **Define what actually justifies waking someone.** Everything else waits for
  morning. Most of what currently interrupts evenings would survive until 09:00
  with no customer noticing.
- **Silence non-urgent notifications outside working hours, at the OS level.**
  Willpower is not a notification policy.

### Communication

- **Async by default is already a stated company value** ("No Bullshit,"
  remote-first, no time-tracking theatrics). Extend it explicitly to response
  time: a stated expectation of same-day, not same-minute.
- **No Slack on the phone after hours**, or at minimum no notifications from it.
  If a true emergency needs to reach a human, that is what a phone call is for —
  and making emergencies use a distinct channel is what allows everything else to
  be ignored safely.
- **Batch email and Slack into windows** rather than running them continuously.
  Continuous partial attention is the mechanism that converts a normal workload
  into an exhausting one.

### The competitive-monitoring boundary

This one is specific to the stated drain and is worth naming as a health
intervention rather than a strategy one:

> **Competitive research happens once a month, in one block, producing one
> document. Not daily. Not in the evening. Not on the phone.**

The strategy is already locked (`CONCLUSIONS.md` §6 — tailwind, not warfare).
Daily monitoring cannot improve a locked decision; it can only supply threat
signal. Cut the input, keep the strategy.

---

## Food and the basics (kept deliberately short)

No diet doctrine — just the parts that interact with this specific working
pattern:

- **Eat on a schedule, not on a gap in the calendar.** Skipped lunches followed
  by late heavy dinners are a sleep problem wearing a food costume.
- **Protein at breakfast and lunch** supports the strength work and steadies
  afternoon energy far more reliably than a coffee does.
- **Hydration is boring and real** — mild dehydration is indistinguishable from
  mild fatigue from the inside.
- **Late heavy meals cost sleep quality.** If dinner is unavoidably late, make it
  lighter.

---

## The recovery layer — the part founders skip

Load without recovery is erosion, not resilience. Recovery here is not a reward
for finishing; there is no finishing.

- **One genuinely off day per week.** Not a "light" day. No Slack, no Sentry, no
  strategy reading. This is the single most commonly skipped item on this list
  and the most restorative.
- **Real holidays, in the calendar, booked in advance, with coverage arranged.**
  The company has a time-off policy (`docs/01-company/time-off-and-absence.md`).
  Founders characteristically do not use their own.
- **A hobby with no revenue attached.** Formaviva is _almost_ this — but only if
  it is capped ([`07`](07-formaviva-adjustments.md)). Uncapped, it becomes a
  second job and stops counting as recovery. That distinction is the whole
  reason the cap exists.
- **Relationships get calendar priority, not residual time.** They are on the
  floor tier of the decision hierarchy, above growth. Treat them that way in
  practice, not just in the document.
- **Time genuinely offline.** Weekends without a laptop; a phone that is not
  within reach at dinner. The nervous system does not distinguish "checking" from
  "working."

---

## What to monitor (the personal dashboard)

Keep it small enough that it survives a bad month. Five things, weekly, one line
each — in a note, not a new app:

| Metric | How | Healthy signal |
|---|---|---|
| **Sleep anchor held** | Nights hitting the wake anchor | ≥5/7 |
| **Movement sessions** | Strength + walks completed | ≥3/week |
| **Off-hours interruptions** | Count of work intrusions after hours | Trending toward 0 |
| **Off day taken** | Yes/no | Yes |
| **Subjective energy** | 1–5, Friday afternoon | ≥3, trending up |

**Rules for this dashboard:** five lines, once a week, no new tooling. The
moment it becomes a project, it is a third venture and it has failed — see the
warning in [`09-technology-leverage.md`](09-technology-leverage.md). Review it in
the Friday close described in
[`04-time-and-attention.md`](04-time-and-attention.md).

**The signal to act on:** subjective energy at ≤2 for three consecutive weeks is
not a motivation problem to push through. It is a load problem, and the response
is subtraction — which is exactly what [`05-decision-framework.md`](05-decision-framework.md)
and [`../PLAN.md`](../PLAN.md) exist to make executable rather than
guilt-inducing.

---

## Sequencing — what to actually start with

Do not adopt this document at once. Adopting it at once is the same failure mode
as the three web front-ends.

1. **Week 1:** book the physical. Set the wake anchor. Turn off after-hours
   notifications.
2. **Week 2–3:** morning light + a daily walk. Take one full off day.
3. **Week 4+:** add strength sessions to the calendar as recurring meetings.
4. **Month 2:** fix the alerting routing so the founder is not a default
   recipient. This one requires a conversation with engineering, which is why it
   is not week one.
5. **Month 3:** book an actual holiday, with coverage.

Five items in three months. That is a pace that survives a bad quarter — which is
the only pace that matters.
