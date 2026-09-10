# Data

*Last updated: YYYY-MM-DD HH:MM*

**The most important document in the project.** Get this right and there's
almost nothing left to guess.

---

## What things are called

One word each. This exact word is used in the code, in the database, and on
screen. No synonyms, ever.

| The thing | What we call it | Not |
|---|---|---|
| a gig the band is playing | **show** | event, gig, concert, date |
| someone who bought a ticket | **buyer** | user, customer, fan, attendee |

*(A synonym in file two is how a codebase starts rotting. Pick and stick.)*

---

## The main thing

### What it holds

| Field | Type | Required | Notes |
|---|---|---|---|
| id | text | yes | |
| | | | |

### Three real examples

**Not made up. Real, with real values. Include one that's awkward.**

```json
[
  { },
  { },
  { }
]
```

*(The third one should be the weird case - the sold-out one, the free one, the
one with a stupidly long name, the one from last year. That's the one that
finds the bugs.)*

### What it can be

<States it moves through. draft → published → sold out → past>

Which changes are allowed, and which aren't:

- draft → published: yes
- published → draft: no, once it's out it's out

---

## The exact rules

**Be specific. This is where guessing does the most damage.**

Anything with maths, sorting, limits, cutoffs, or "this counts as that":

- Prices are stored in pence as whole numbers. Never floats. `1250` is £12.50.
- Shows sort soonest first. Past shows don't appear at all.
- A show is "past" after midnight on the day, not at the start time.
- Sold out means tickets sold >= capacity. Capacity includes the guest list.

---

## Must never happen

- Two buyers with the same ticket number
- A ticket for a show that's already happened
- A price of zero unless the show is explicitly marked free

---

## Where it lives

**Stored in:** <a json file / a database / the browser>
**Kept for:** <how long>
**Backed up:** <how, or "not at all, and that's accepted">

## Private or sensitive

| What | How sensitive | Who can see it |
|---|---|---|
| email | personal | only the band |

**If someone asks to be deleted:** <what actually happens>

## Where in the world

- Currency: <GBP - and it shows as £, not $>
- Dates: <DD/MM/YYYY>
- Timezone: <Europe/London>
- Language: <English (UK) - "colour", not "color">

*(Without this I default to US English, dollars and MM/DD, silently.)*
