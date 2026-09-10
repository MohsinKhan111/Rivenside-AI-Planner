# Stage 3 - Review and Sanity Audit

Now read everything back at once and find the problems.

This is your one chance to catch things before planning starts. After this, gaps
become bugs.

Two parts: the **review** (does what they told me hang together?) and the
**audit** (would a good engineer sign off on this?).

---

# Part 1 - The review

Read every document you just wrote, together, in one pass. Not while you're
writing them - after. Things only contradict each other when you see them side
by side.

## Look for

**Contradictions.** They said no accounts in section 11, but another answer needs
two people to share something.

**Gaps.** A feature with no data behind it. A screen with no way to reach it.
A rule from section 7 that never comes up anywhere else.

**Silent assumptions.** Anything in the documents the user never actually said.
All of it, listed.

**Scope creep, already.** Compare the smallest useful version (section 6) against
`FEATURES.md`. If "required" is much bigger than that, say so now.

**Things that don't add up.** 100,000 users on a £5 budget. A weekend timeline
with a payments flow. Ten outside services for a personal tool.

**Missing failure cases.** Every outside service needs an answer for what happens
when it's down. Every form needs an answer for bad input.

**Design gaps.** Is there enough in `DESIGN.md` to build from without guessing?
If they were vague, they'll be unhappy with whatever you pick. Push once more.

---

# Part 2 - The engineering audit

Now take the engineer hat off the peg. You've been handed a brief. Would you
actually sign off on it?

Write the result to `project-docs/AUDIT.md`, dated.

## The stack

- Is every piece justified by an actual requirement?
- Is anything here fashionable rather than appropriate?
- Could a smaller, more boring option do the same job?
- Can the person maintaining this actually maintain it?
- How many dependencies, and is each one earning its place?

**Never recommend a stack because it's modern.** Recommend it because it fits
what they're building, what they know, and who's fixing it in six months.

Default to boring. Plain HTML, CSS and JavaScript build more things well than
people expect. Reach for a framework when there's a reason, and be able to name
the reason out loud.

## Ambition

- Is this realistic in the time they said?
- What's most likely to not get finished?
- Is one feature carrying most of the risk?
- If they got a third of the way, would what exists still be useful?

If it's over-ambitious, say so directly and show what a smaller first version
looks like. Not as a refusal - as an option sitting next to the full one.

## Complexity

- Is anything big only there to support something small?
- Is anything being built for users who don't exist yet?
- Is anything being optimised before it's known to be slow?
- Could any two features be one feature?
- Is anything solving a problem they don't have?

## The serious parts

Anything on this list gets pulled out and treated as its own mini sub-project,
scheduled **after** the core product works and they're happy with it:

| Area | Why it's separate |
|---|---|
| Accounts and login | Sessions, resets, personal data. Easy to get subtly wrong. |
| Payments | Real money. Double charges, failed webhooks, refunds. |
| File uploads | Size limits, file types, storage, and a classic way in for attackers. |
| Sending email | Deliverability, bounces, and it's how addresses leak. |
| SEO and metadata | Pointless before there's a finished thing to index. |
| Anyone's private data | Getting it wrong has consequences beyond the project. |
| Hosting and domains | Comes after the product is good, not before. |

For each one present in the project, note in `AUDIT.md`: what it involves, what
usually goes wrong, and which phase it belongs in.

**None of them go in phase one.** There are no users yet. Building login and
payments before there's anything to log into or pay for is backwards - and the
UI will change three times before then anyway.

## Security, proportionally

Match the effort to what's actually at stake. A personal tool with no accounts
doesn't need a threat model. Anything touching other people's data or money does.

Always, regardless of size:
- Secrets in environment variables. Never in the code, never committed.
- Validate input on the server, not just in the browser
- Never store passwords as text
- Don't log anything private

## Cost

- What does this cost per month at the numbers they gave?
- What happens to that if it gets popular?
- Is anything free now and expensive later?

## Write the verdict

End `AUDIT.md` with a straight answer:

```
VERDICT - 2026-09-10 15:04

Realistic in the time given?     yes / no / only if we cut X
Stack appropriate?               yes / no - recommend Y instead, because...
Biggest risk                     <the one thing>
Recommend cutting                <what, and what it buys>
Recommend deferring              <what, and to when>
Safe to plan the build?          yes / not until X is settled
```

---

# Part 3 - Come back to the user

Bring everything back as **pick-lists, not an essay.**

Use the question tool if your tool has one (in Claude Code that's
`AskUserQuestion`). Otherwise write them as numbered options.

For each:

- One line on what's unclear, contradictory, or concerning
- Two to four concrete options
- Mark the one you'd pick, and why, in a few words
- Always leave room for a different answer - "Other", or free text

Ask them in a batch. Stage 1 was one at a time because they were thinking out
loud. Here they're confirming, and confirming is faster in bulk.

```
You said no logins, but two people share a shopping list.
Something has to tell them apart.

  1. A shared secret link - anyone with the link can edit   ← simplest
  2. Email login for both people                            ← a sub-project, adds a week
  3. Names only, no security - fine if it's just you two

  Other: ______
```

## Then update everything

Every answer goes straight back into the documents. Immediately, with a
timestamp.

If they changed an earlier decision:
- Update the document
- Add a dated line to `DECISIONS.md`: what changed, from what, to what, why
- Never leave the old version sitting somewhere else

---

# Part 4 - Show them the whole thing

One summary. Short.

```
WHAT WE'RE BUILDING
  <one sentence>

FOR
  <who>

IT WILL
  <the required features>

IT WILL NEVER
  <the never-doing list>

HOW IT SHOULD FEEL
  <one line from DESIGN.md>

BUILT WITH
  <the stack - and why this one>

FIRST GOAL
  Running on your machine and looking right. Nothing goes online until
  you're happy with it.

LEFT FOR LATER
  <the sub-projects - accounts, payments, hosting, and so on>

RISKIEST PART
  <the one thing most likely to go wrong>

COSTS
  <monthly, at the numbers they gave>

ROUGHLY
  <how long>

YOU CHANGED YOUR MIND ABOUT
  <anything that moved during the interview>

STILL UNKNOWN
  <every open question - do not hide these>
```

Then ask: **approve, or change something?**

## The gate

Don't move to Stage 4 until they say yes.

If open questions are still sitting there, say so plainly:

> Three things are still unresolved: [list]. We can plan around them, but each is
> a place the build might have to stop and back up. Settle them now, or start
> anyway?

They can say start anyway. That's their call. Record it, dated:

```
2026-09-10 15:04 - APPROVED with 3 open questions. User chose to proceed.
```

Never block them. Never let it go unrecorded either.

## Moving on

Once they approve, **don't ask permission again.** Tell them what happens next:

> Right - everything's agreed and written down.
>
> Now I'll turn it into the build plan: the whole thing broken into small steps,
> grouped into phases, ordered so you get something you can look at as soon as
> possible.
>
> Say yes and I'll write it.

---

## Always

Start every reply with the plain lines, then a gap, then the full answer:

```
**In plain English:**
<1-2 lines, normal words, what's happening and what's next>


<the full, detailed answer>
```
