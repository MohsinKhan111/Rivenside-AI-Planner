# Worked example

A real one, shortened. A band selling tickets to its own shows.

This is what comes out the other end. Six documents, 34 steps, built in a week.
Nothing else was needed.

---

## What the interview caught

Three things that would have cost weeks:

**Accounts.** They wanted logins so buyers could see their tickets. Asked what
breaks without one - nothing. The ticket goes to their email. Cut passwords,
resets, personal data storage, and support work.

**A database.** Ten shows a year, ~30 tickets a week. That's a JSON file. No
database, no hosting bill, no migrations.

**"Maybe we'll add merch later."** Marked `LATER`, not built. Three weeks in
they asked for it. The plan said what it'd cost. They said not yet.

---

## RULES.md

```markdown
# Rules

## What this is
A one-page site where fans of one band buy tickets to that band's shows.

## Hard limits
- No user accounts. Ever. Tickets go to email.
- No database. Shows live in `data/shows.json`. Sales in `data/sales.json`.
- Card details never touch this project. Stripe handles them.
- Prices are whole numbers of pence. Never floats.
- Nothing is stored about a person except email and what they bought.

## Built with
- Node 22, plain JavaScript
- Hono (routing)
- Stripe (payment)
- Resend (email)
- Hosted on Fly.io

Anything not on this list needs an entry in DECISIONS.md first.

## Never doing
- Seat selection
- A phone app
- Selling other bands' tickets
- Accounts

## Before you change anything
1. Read this file
2. Check it's in FEATURES.md and marked required
3. Smallest change that works
4. Run it before saying it's done
```

---

## FEATURES.md, shortened

| # | Feature | Status |
|---|---|---|
| F1 | List upcoming shows | REQUIRED |
| F2 | Buy a ticket | REQUIRED |
| F3 | Email the ticket | REQUIRED |
| F4 | Band sees who's coming | REQUIRED |
| F5 | Sold-out marking | REQUIRED |
| F10 | Discount codes | OPTIONAL |
| F20 | Merch | LATER |
| F30 | Seat selection | NO - standing venues only |

---

## DATA.md, the part that mattered

```markdown
## What things are called
a gig      → **show**   (not: event, gig, concert, date)
a purchase → **sale**   (not: order, ticket, transaction)

## Three real shows
[
  { "id": "s1", "date": "2026-10-04", "venue": "The Lexington",
    "city": "London", "pricePence": 1200, "capacity": 200 },
  { "id": "s2", "date": "2026-10-11", "venue": "Hare & Hounds",
    "city": "Birmingham", "pricePence": 1000, "capacity": 150 },
  { "id": "s3", "date": "2026-09-02", "venue": "Brudenell Social Club",
    "city": "Leeds", "pricePence": 0, "capacity": 400 }
]

s3 is the awkward one on purpose: it's free, it's in the past, and it's
the biggest room. It found three bugs.

## The exact rules
- Sort soonest first. Past shows don't appear at all.
- "Past" means after midnight on the day, not after the start time.
- Sold out when sales >= capacity. Capacity includes guest list.
- pricePence of 0 means free - skip Stripe entirely, still send a ticket.

## Where in the world
GBP, shown as £. Dates DD/MM/YYYY. Europe/London. English (UK).
```

That last block is why nothing came out in dollars.

---

## BUILD-PLAN.md, one step

```markdown
### Step 14 - Show the list of shows

**Why:** F1 - fans need to see what's on before they can buy
**Touches:** `src/pages/shows.js`, `src/data/shows.json`
**Needs:** Step 9 (the data file exists)

**Do:**
- Read shows from `data/shows.json`
- Soonest first
- Each row: date, venue, city, price, Buy button
- Past shows don't appear
- Free shows show "Free", not "£0.00"
- If nothing upcoming: "No shows announced yet"

**Done when:** /shows lists s1 and s2 in date order. s3 does not appear.

**Careful:** Dates are DD/MM/YYYY, Europe/London. Prices are pence - divide by
100 and show with £. A show is past after midnight on the day, not the start time.
```

Note the **Careful** line repeats the rules from DATA.md in full. That's on
purpose. A session doing step 14 shouldn't have to go and find them.

---

## Numbers

| | |
|---|---|
| Questions asked | 31 of 96 (small project) |
| Interview | ~25 minutes |
| Documents | 6 |
| Build steps | 34 |
| Build time | 6 days, evenings |
| Running cost | £0/month + Stripe's cut |
| Things cut in the interview | 3 |
| Times it drifted | 0 |
