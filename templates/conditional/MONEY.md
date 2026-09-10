# Money

*Last updated: YYYY-MM-DD HH:MM*

*Only if something is being sold.*

**The one rule:** card details never touch this project. A payment provider
handles them. There is no version of this where handling cards yourself is worth
it.

---

## What's being sold

| Thing | Price | One-time or ongoing |
|---|---|---|
| | | |

## Free version

<What's free, what the limit is, what happens at the limit.>

## Provider

<Stripe / Paddle / other>

Why: <>
What we store: <a payment id, nothing else>

## Prices

- Currency: <>
- Stored as: **whole numbers of the smallest unit** - pence, cents. Never
  floats. `1250` means £12.50.
- Tax / VAT: <included? added? handled by the provider?>

## When payment fails

<What the user sees. Is anything held? Do they get an email? Can they retry?>

## Refunds

<Through the app, or by hand? Who can do it? What happens to what they bought?>

## They stop paying

<What happens to their stuff. How much warning. Is it deleted or just locked?>

## Getting it wrong

- Double charges: <what stops one>
- Charged but nothing delivered: <how you find out>
- Delivered but not charged: <how you find out>

If any of those three has no answer, the build stops at that step.
