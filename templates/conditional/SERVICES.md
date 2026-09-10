# Outside services

*Last updated: YYYY-MM-DD HH:MM*

*Only if this depends on anything it doesn't control.*

Every one of these is something that can break, cost money, change its rules, or
disappear. Each needs a reason.

---

| Service | What for | Why not something simpler | If it's down | Cost |
|---|---|---|---|---|
| Stripe | taking payment | Cards can't be handled ourselves | No sales. Message shown. | 1.5% + 20p |
| Resend | sending tickets | Could use a plain SMTP account, but delivery is worse | Payment works, ticket retries | free under 3k/mo |

---

## Keys and secrets

- Kept in: <environment variables - never in the code, never in git>
- `.env` is in `.gitignore`: <yes>
- If a key leaks: <how to rotate it, and who can>

## Rules and limits

| Service | Limit | What happens at the limit |
|---|---|---|
| | | |

## If one disappears

| Service | Replaceable with | How painful |
|---|---|---|
| | | |

*(Anything marked "very painful" is a real risk. Say so in the review round.)*
