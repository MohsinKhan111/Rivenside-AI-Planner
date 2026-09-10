# Engineering audit

*Last updated: YYYY-MM-DD HH:MM*

The sanity check before planning. Written as a working engineer looking at a
brief and deciding whether to sign off on it.

---

## The stack

| Piece | Why it's here | Could something simpler do it? |
|---|---|---|
| | | |

**Dependency count:** <n>
**Can the maintainer maintain it?** <yes / no - and what to do about it>
**Anything here that's fashionable rather than appropriate?** <>

## Ambition

**Realistic in the time given?** <>
**Most likely thing to not get finished:** <>
**One feature carrying most of the risk:** <>
**If they got a third of the way, still useful?** <>

## Complexity found

| What | Why it's more than it needs to be | Suggested instead |
|---|---|---|
| | | |

## Sub-projects

Pulled out and scheduled after the core product works.

| Area | What it involves | What usually goes wrong | Phase |
|---|---|---|---|
| Accounts | | | 5 |
| Payments | | | 6 |
| Going live | | | last |

## Security

**What's actually at stake:** <nothing much / other people's data / money>
**Proportional response:** <>

Always true:
- [ ] Secrets in environment variables, not in the code, not committed
- [ ] Input validated on the server, not just in the browser
- [ ] Passwords never stored as text
- [ ] Nothing private in logs

## Cost

| | |
|---|---|
| Per month at their numbers | |
| If it gets popular | |
| Free now, expensive later | |

---

## VERDICT

*Date: YYYY-MM-DD HH:MM*

| | |
|---|---|
| Realistic in the time given? | yes / no / only if we cut X |
| Stack appropriate? | yes / no - recommend Y instead, because... |
| Biggest risk | |
| Recommend cutting | |
| Recommend deferring | |
| Safe to plan the build? | yes / not until X is settled |

## What the user decided

| Date | I recommended | They chose | Recorded as |
|---|---|---|---|
| | | | D<n> |
