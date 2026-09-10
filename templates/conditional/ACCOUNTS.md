# Accounts

*Last updated: YYYY-MM-DD HH:MM*

*Only if people log in.*

**First, honestly:** what breaks if there's no login at all? Accounts bring
passwords, resets, personal data, and support work forever. If a link or an
email does the same job, use that instead - and record why in `DECISIONS.md`.

---

## Why there's a login

<The actual reason. "It feels professional" is not a reason.>

## How they log in

<email link / password / Google / something else>

Why that one: <>

## Who can do what

| Role | Can | Can't |
|---|---|---|
| visitor | see public things | |
| member | | |
| owner | everything | |

Rule: check permissions on the server, every time. Hiding a button is not
security.

## Sessions

- Stays logged in for: <>
- Logged out when: <>
- On another device: <>

## Forgot their login

<What happens. Automatic, or you deal with it by hand?>

## Deleting an account

<What actually gets removed, what's kept, how long.>

## Passwords

If passwords are used at all:
- Never stored as-is. Hashed, with a real library, never by hand.
- Never logged, never emailed, never shown.
- Minimum: length only. No silly character rules.
