# Stage 2 - The Documents

Turn the answers into documents. Only the ones this project actually needs.

---

## The checklist

Go through this list. Tick what applies. Show the user the ticked list before
you write anything.

### Always

| Document | What it holds |
|---|---|
| `RULES.md` | The hard limits. Short. **This is the one that gets re-read every session.** |
| `PROJECT.md` | What it is, who it's for, what it will never do |
| `FEATURES.md` | Numbered list, each marked required / optional / later / no |
| `DATA.md` | What things are called, the three real examples, the exact rules |
| `DESIGN.md` | How it should look and feel. **Always** - they care about this most |
| `DECISIONS.md` | Why choices were made. Append-only |
| `OPEN.md` | What's still unknown |

### Only if it applies

| Document | Add it when |
|---|---|
| `JOURNEY.md` | There are screens and a flow through them |
| `ACCOUNTS.md` | People log in |
| `MONEY.md` | Something is being sold |
| `SERVICES.md` | It depends on anything outside itself |
| `FAILURES.md` | It touches the network, outside services, or other people's data |
| `MIGRATION.md` | There's existing data or an existing app to move from |

### Written later

| Document | When |
|---|---|
| `AUDIT.md` | Stage 3, the engineering sanity check |
| `BUILD-PLAN.md` | Stage 4, after the user approves |
| `PROGRESS.md` | Stage 4, alongside the plan |

---

## Rules for writing them

**Date everything.** Every document starts with a `Last updated: YYYY-MM-DD HH:MM`
line, and every entry that can carry a timestamp gets one. Without dates you
can't tell what changed when, and you can't catch drift.

**Don't create a document you can't fill.** A file with three placeholder lines
is worse than no file. If a section would be that thin, fold it into `PROJECT.md`
and say so.

**Small project, few documents.** A weekend tool gets six files. A payments app
gets eleven. If you're writing eleven for a weekend tool, stop - you've become
the problem this exists to solve.

**Every fact traces back to an answer.** If something appears in a document that
the user never said, it's an `ASSUMPTION` and it goes in `OPEN.md` too.

**Number the features.** `F1`, `F2`, `F3`. The build plan refers to these
numbers. Without them, "does the build match the plan" is guesswork.

**Use their words.** The name they chose in section 7 (The things in it) is the name in the documents, in
the code, and on screen. Never introduce a synonym.

**`RULES.md` must fit on one screen.** It gets read at the start of every
session forever. Long means skipped. Aim for under 40 lines.

---

## What goes in RULES.md

This is the most important file in the project. It is not general advice - every
line must be specific to *this* project and checkable.

Bad: "Don't add unnecessary dependencies."
Good: "This project uses three libraries: X, Y, Z. A fourth needs a new entry in DECISIONS.md."

Bad: "Keep it simple."
Good: "There is no database. Data lives in `data/*.json`. If you think a database is needed, stop and say why."

Five parts:
1. **What this is** - one sentence
2. **Hard limits** - three to seven specific rules from the interview
3. **The whole stack** - everything it's built with, listed. Anything not on the list needs a decision recorded.
4. **Never doing** - the rejected list, word for word from section 6 (What it is not)
5. **Before you change anything** - read this file, check the feature is in `FEATURES.md`, make the smallest change that works

---

## Also write the pointer file

Create `CLAUDE.md` in the project root (and `AGENTS.md` alongside it, same
content, for other tools):

```
Read project-docs/RULES.md before changing anything in this project.
For feature work, also read PROJECT.md and FEATURES.md.
Building? Follow project-docs/BUILD-PLAN.md in order and update PROGRESS.md.
Changing a decision means adding to project-docs/DECISIONS.md. Never edit past entries.
```

This is the only thing a fresh session sees on its own. Everything else depends
on it.

---

## When the documents are written

Show the user the list of files created and roughly what's in each. Then move to
`stages/3-REVIEW.md`.

---

## Always

Start every reply with the plain lines, then a gap, then the full answer:

```
**In plain English:**
<1-2 lines, normal words, what's happening and what's next>


<the full, detailed answer>
```
