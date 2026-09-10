# Stage 4 - The Build Plan

Turn the documents into steps, grouped into phases.

This is the point of everything before it. The plan has to be good enough that a
fresh session, with none of this conversation available, can pick up any step
and do it right.

---

## The test for a good step

**Could someone who has never seen this project do this step, having read only
the step itself and `RULES.md`?**

If no, it's too big or too vague. Split it.

"Build the checkout" fails. "Add a POST /checkout route that takes a cart id,
calls Stripe, and returns the session url" passes.

## Sizing

- One step is 15-45 minutes of work
- One step touches one to three files
- One step leaves the project **working**, not half-broken
- 30 steps for something small. 100+ for something real. The number doesn't
  matter - the size of each one does.

120 obvious steps beat 40 that need thinking about.

---

## Phases

Group the steps into phases. A phase is a stopping point where the user can look
at something and have an opinion about it.

**The order is always this shape:**

### Phase 1 - Something on screen
Running locally and looking roughly right. Real layout, real fonts, real
colours, fake data. Nothing works yet.

This comes first because it's what they actually care about, and because
everything after is easier when there's something to look at. They'll change
their mind about half the design the moment they see it - which is exactly what
should happen, and it should happen now, not after the database is wired up.

### Phase 2 - The main thing, working
The core journey from section 4, end to end, with real data. Still local. Still
no accounts, no payments, no hosting.

### Phase 3 - The rest of required
Everything else marked `REQUIRED` in `FEATURES.md`.

### Phase 4 - Polish
Empty states, error messages, loading, mobile, the small stuff. Unless they asked
for polished (section 20) - then polish lives inside every step and this phase is
just the leftovers.

### Phase 5+ - The sub-projects, one at a time
Accounts. Payments. Uploads. Email. Each is its own phase with its own small plan
and its own checks. Never two at once.

### Last - Going live
Hosting, domain, deployment. Only when they're happy with the product and ask for
it. **Do not schedule this early and do not bring it up unprompted.**

---

## Rules about ordering

**Local first, always.** Nothing in phases 1-4 needs an internet connection, a
hosting account, or a domain. If something seems to, find another way - fake
data, a local file, a stub.

**Riskiest thing early, but inside its phase.** If there's an odd API or a
library nobody's sure about, find out in phase 2, not phase 5.

**Never build `LATER` or `OPTIONAL` before every `REQUIRED` is done.**

**Never put a sub-project before phase 5.** There are no users yet. Nothing to
log into. Nothing to pay for. And the UI will change three times before then.

---

## What each step looks like

```markdown
### Step 14 - Show the list of shows

**Why:** F3 - fans need to see what's on before they can buy
**Touches:** `src/pages/shows.jsx`, `src/data/shows.json`
**Needs:** Step 9 (the data file exists)

**Do:**
- Read shows from `data/shows.json`
- Show them soonest first
- Each row: date, venue, city, price, and a Buy button
- Past shows don't appear
- If there are no upcoming shows, say "No shows announced yet"

**Done when:** Loading /shows lists the three real examples from DATA.md, in
date order, with the past one not showing.

**Careful:** Dates are UK format (DATA.md). Prices are pence - divide by 100 and
show with £. A show is past after midnight on the day, not the start time.
```

Every step has all six: why, touches, needs, do, done when, careful.

The **why** points at a feature number from `FEATURES.md`. A step that doesn't
trace back to a feature shouldn't exist. Delete it.

The **careful** line carries what would otherwise be forgotten - the exact rules
from `DATA.md`, the currency and date format, the thing that must never happen.
**Repeat it in full in every step it applies to.** Repetition is cheap.
Re-reading the whole project is not. This is the line that makes wider context
unnecessary.

---

## Also write PROGRESS.md

```markdown
# Progress

Last worked on: 2026-09-10 15:04
Currently on: Phase 2, Step 14

## Phase 1 - Something on screen   ✅ finished 2026-09-08 19:20
- [x] Step 1 - ...

## Phase 2 - The main thing, working   ← here
- [x] Step 13 - ...
- [ ] Step 14 - Show the list of shows   ← here
```

Dates on everything. This is how drift gets spotted.

---

## Before you show it

Check:

- Every required feature has at least one step
- Every step points at a feature
- No step depends on a step that comes after it
- No step needs knowledge that isn't written down somewhere
- Nothing contradicts `RULES.md`
- Nothing in phases 1-4 needs hosting or an internet connection
- No sub-project appears before phase 5

---

## How to hand it over

Don't just dump the plan. Tell them how it's going to go.

> The plan's written. <N> steps, in <M> phases.
>
> **How this works:** I'll go one step at a time and show you as I go. At the
> end of each phase I'll stop, show you what's there, and give you a summary of
> what got done - then you decide whether to carry on or change something.
>
> **Phase 1** gets something on screen you can actually look at. Nothing will
> work yet, but you'll see the real layout and colours. That's deliberate -
> you'll have opinions once you can see it, and it's much cheaper to change now
> than later.
>
> **Phase 2** makes the main thing actually work.
>
> Everything stays on your machine until you're happy with it. Accounts,
> payments and putting it online come later, each handled properly on its own.
>
> Ready to start?

Then list:
- The phases, one line each
- Which steps are risky, and what happens if one goes wrong
- What's deliberately not in the plan (the `LATER` and `NO` lists), so nobody
  wonders whether it was forgotten

**Once they say go, open `stages/5-BUILDING.md`.**

---

## Always

Start every reply with the plain lines, then a gap, then the full answer:

```
**In plain English:**
<1-2 lines, normal words, what's happening and what's next>


<the full, detailed answer>
```
