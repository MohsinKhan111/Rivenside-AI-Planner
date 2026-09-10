# When things break

*Last updated: YYYY-MM-DD HH:MM*

*Only if this touches the network, outside services, or other people's data.*

Every one of these has an answer, or it becomes a bug someone finds at the worst
possible moment.

---

## Outside services

| Service | If it's down | User sees |
|---|---|---|
| Stripe | Can't take payment | "Payments are down, try in a few minutes" - nothing is charged |
| Email | Ticket doesn't send | Payment still goes through. Retry. Band notified. |

## The network

**Drops mid-action:** <what happens>
**Slow:** <spinner? skeleton? how long before something is said?>

## Bad input

| Where | Bad input | What happens |
|---|---|---|
| email field | not an email | Message under the field. Nothing submits. |

Rule: check on the server, not just in the browser. Anything in the browser can
be bypassed.

## Repeats and collisions

**Button pressed 20 times:** <disabled after first? one charge only?>
**Two people change the same thing:** <who wins, and does the other one know?>
**The same request arrives twice:** <can it happen? what stops a double charge?>

## Abuse

| What someone might do | What stops it |
|---|---|
| Hammer the form | Rate limit - <n> per minute per IP |
| Guess ticket links | Long random ids, not sequential numbers |

## When something does go wrong

- Where does the error get recorded?
- Does anyone find out, or does it sit silently?
- Do errors ever show a user something private? *(They must not.)*
