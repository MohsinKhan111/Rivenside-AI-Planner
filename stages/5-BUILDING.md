# Stage 5 - Building

The plan exists. Now follow it.

This file is for every session from here on, including sessions that know nothing
about how the project started.

---

## Every session, before touching anything

1. Read `project-docs/RULES.md`
2. Read `project-docs/PROGRESS.md` - find where you are
3. Read the current step in `project-docs/BUILD-PLAN.md`
4. Do that step
5. Tick it off in `PROGRESS.md`, **with the date and time**

That's it. You don't need to read everything. The step is supposed to be enough.
If it isn't, the step was written badly - fix the step, then do it.

---

## One step at a time

Unless they asked for bigger chunks (section 20), do one step, then stop and show
them.

Don't run ahead. Don't do step 15 because you're already in the file. Steps are
sized so nothing is lost when a session ends.

---

## At the end of every phase - stop and report

This is the rhythm the user was promised. Don't skip it.

```
PHASE 2 DONE - The main thing, working
Finished 2026-09-10 15:04

What got built
 - Fans can see the list of shows
 - They can pick one and go to a checkout page
 - Prices and dates show correctly in UK format

What you can do right now
  Run `npm run dev` and open localhost:3000. Click through a show.

What isn't there yet
  Payment doesn't actually take money - that's phase 5.
  No emails go out yet.

Anything I had to decide
  The date library defaulted to US format. Forced it to UK. (D7)

Next up
  Phase 3 - the rest of the required features. <n> steps.

Carry on, or change something?
```

Then wait. A phase boundary is where they're most likely to want something
different, and it's the cheapest moment to change it.

---

## Stay local

Nothing goes online until they ask. No hosting, no domains, no deployment, no
"shall we put this live?". Get it working on their machine and looking right.

If a step genuinely can't be done locally, say why, keep it minimal, and get back
to the product.

---

## When the user asks for something new mid-build

This is the moment projects die. Handle it properly.

1. **Check `FEATURES.md`.** Is it there?
  - `REQUIRED` - fine, it's planned. Where's its step?
  - `LATER` or `NO` - say so: *"This was marked 'later' on day one. Want to move it up? Costs roughly X, and it pushes Y back."*
  - Not there at all - it's new. Go to 2.

2. **Check `RULES.md`.** Does it break a hard limit? If yes, say which line, and
   what it would take to change it. Don't just do it.

3. **Is it a sub-project?** Accounts, payments, uploads, email, anything touching
   private data - it doesn't get bolted on mid-phase. It gets its own phase, its
   own small plan, and it happens after the current phase finishes.

4. **Say what it costs** before building. Which steps change. What might break.

5. **If they still want it** - add it to `FEATURES.md`, add steps to
   `BUILD-PLAN.md`, add a dated line to `DECISIONS.md`. Then build it.

Never quietly bolt a feature on. That's how a project ends up at 5fps with nobody
knowing when it happened.

---

## When you find out the plan was wrong

It happens. Something in the documents turns out to be untrue once real code
exists.

**Do not silently work around it.**

1. Stop.
2. Write what you found in `PROGRESS.md` under Notes, with the date and time.
3. Say which documents are now wrong.
4. Fix those documents.
5. Fix the affected steps.
6. Add to `DECISIONS.md`: what we thought, what's actually true, what changed.
7. Then carry on.

A wrong assumption caught and recorded costs an hour. One that gets patched
around costs the project.

---

## What not to do

- Don't refactor things you weren't asked to touch
- Don't rewrite something that works because you'd have written it differently
- Don't add a library that isn't in `RULES.md`
- Don't add tests, types, comments, or tooling nobody asked for
- Don't optimise anything until it's actually slow
- Don't build for users who don't exist yet
- Don't suggest hosting, domains, or going live unprompted
- Don't say something's done without running it

---

## Checking in on the whole project

At every phase boundary, and whenever they ask, do a quick pass:

- Does anything in the code have no feature number behind it?
- Is any required feature still not built?
- Are there libraries installed that `RULES.md` doesn't list?
- Does the code do anything the documents say it doesn't?
- Are there open questions in `OPEN.md` that matter now?
- Has the thing drifted from what they described at the start?

**Report what you find. Don't fix it.** They decide what changes.

Write findings to `project-docs/CHECKS/YYYY-MM-DD-HHMM.md` so the next one can
see what was already known about.

---

## Always

Start every reply with the plain lines, then a gap, then the full answer:

```
**In plain English:**
<1-2 lines, normal words, what's happening and what's next>


<the full, detailed answer>
```
