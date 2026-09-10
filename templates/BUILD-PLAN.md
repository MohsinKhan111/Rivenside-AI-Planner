# Build plan

*Last updated: YYYY-MM-DD HH:MM*

<N> steps. Roughly <time>.

Each step is small enough to do without knowing anything about the rest of the
project. That's deliberate - it means a fresh session can pick up any step and
get it right.

---

## Phases

| Phase | What | Steps | Status |
|---|---|---|---|
| 1 | Something on screen - local, looks right, nothing works yet | 1-<n> | |
| 2 | The main thing, working - local, real data | <n>-<n> | |
| 3 | The rest of the required features | <n>-<n> | |
| 4 | Polish - empty states, errors, mobile | <n>-<n> | |
| 5 | <sub-project, e.g. accounts> | <n>-<n> | |
| last | Going live - only when they ask | <n>-<n> | |

Nothing in phases 1-4 needs the internet, hosting, or a domain. Everything runs
on their machine.

I stop at the end of every phase, show what's there, and summarise what got done.

## Risky steps

| Step | Why it's risky | If it goes wrong |
|---|---|---|
| 8 | First time talking to Stripe | Fall back to a manual payment link |

## Left for later

Sub-projects, each handled on its own once the product works:

| Area | Phase | Why not sooner |
|---|---|---|
| Accounts | 5 | Nothing to log into yet |
| Payments | 6 | Nothing to pay for yet |
| Hosting | last | Product should be good first |

## Not in this plan

Everything marked `LATER` or `NO` in `FEATURES.md`. Listed here so nobody
wonders whether it was forgotten:

- F20 <thing>
- F30 <thing>

---

### Step 1 - <name>

**Why:** F<n> - <the feature this serves>
**Touches:** `path/to/file`
**Needs:** <earlier step, or "nothing">

**Do:**
- <specific instruction>
- <specific instruction>

**Done when:** <something you can actually check by looking>

**Careful:** <the rule from DATA.md that applies here, repeated in full>

---

### Step 2 - <name>

**Why:**
**Touches:**
**Needs:**

**Do:**
-

**Done when:**

**Careful:**

---

*(Repeat. Every step has all six lines. A step with no **Why** pointing at a
feature number shouldn't exist.)*
