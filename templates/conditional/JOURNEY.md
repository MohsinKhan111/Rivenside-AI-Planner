# Journey

*Last updated: YYYY-MM-DD HH:MM*

*Only if there are screens.*

Every screen, and how you get between them. If a screen has no way in, it's a
bug in the plan, not in the code.

---

## Screens

| Screen | What's on it | You get here from |
|---|---|---|
| Home | list of shows | landing, or the logo |
| Show | one show, buy button | Home |
| Paid | ticket sent confirmation | Show, after payment |

## The main journey

1. Lands on Home
2. Sees the list of shows
3. Taps one
4. Taps Buy
5. Pays
6. Sees "check your email"
7. Ticket arrives

## What happens after each action

| They do | Then |
|---|---|
| Tap Buy | Straight to payment. No account step. |
| Pay | Confirmation screen + email within 30 seconds |
| Payment fails | Back to the show, message explaining, cart kept |

## Empty and error states

Every screen needs an answer for both.

| Screen | Nothing there yet | Something went wrong |
|---|---|---|
| Home | "No shows announced yet" | "Can't load shows - try again" |
