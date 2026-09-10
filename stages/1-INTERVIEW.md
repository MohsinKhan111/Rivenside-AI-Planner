# Stage 1 - The Interview

Ask these questions. One at a time. Write every answer to
`project-docs/ANSWERS.md` as you go.

---

## How to ask

- **One question per message.** Wait for the answer before the next one.
- **Adapt.** If an answer already covers a later question, skip it and say so.
- **Skip whole sections** that don't apply. No payments? Skip section 12.
- **"I don't know" is valid.** Record it as `OPEN`, say what you'd assume, move
  on. Never stall on one question.
- **Follow up when an answer is vague**, but no more than twice. Then move on
  and mark it `OPEN`.
- **Show your working.** If an answer changes the shape of the project, say so
  in one line before the next question.

## How deep to go

Section 0 tells you. Then:

| Project | Ask |
|---|---|
| Just for you, no money, no accounts | Sections 0-7, 10, 17, 20. ~20 questions |
| Real users, stores data | Add 8, 9, 11, 13-16, 18, 19 |
| Money, private data, or a team | All of it |

Don't run all 20 sections on a weekend project. That's the same mistake in a
different direction.

---

## 0. SIZE CHECK

1. What are you building, in one sentence?
2. Is this for you, or for other people?
3. Roughly how long do you think this should take - a weekend, a few weeks, longer?

## 1. THE IDEA

4. What problem does this solve?
5. Who has this problem right now?
6. How do they deal with it today, without your thing?
7. Why does this need to exist?

## 2. WHAT ALREADY EXISTS

*Ask this early. It changes everything downstream.*

8. Is there any code already, or are we starting from nothing?
9. Do you have a logo, brand colours, or a design file?
10. Do you own a domain?
11. Do you already have accounts set up anywhere - hosting, Stripe, a database, an email service?
12. Is there existing data - a spreadsheet, an old app, anything to bring over?
13. Have you tried building this before? What went wrong?

## 3. THE USER

14. Who is this for?
15. Who is it *not* for?
16. Are they comfortable with tech, or not really?
17. Realistically, how many people use this in the first month?
18. Do different kinds of people use it differently? *(If yes, this opens section 11.)*

## 4. WHAT THEY ACTUALLY DO

19. Someone lands on it for the first time. What do they see?
20. What's the very first thing they do?
21. Walk me through the main thing they came here for, start to finish.
22. What happens right after they finish that?
23. What makes them come back?

## 5. FEATURES

24. What must exist on day one, or the thing is pointless?
25. What would be nice, but you could launch without?
26. What are you imagining for "later"?

## 6. WHAT IT IS NOT

*This section is what stops the project drifting later. Don't skip it.*

27. Name three things this will never do.
28. Six months from now someone asks for a new feature. What would make you say no?
29. What's the smallest version of this that's still worth using?

## 7. THE THINGS IN IT

*The most important section. Everything else gets easier once this is answered.*

30. What are the main things your app deals with? Name them. *(orders, recipes, players, invoices, messages...)*
31. What do you want each one called? Pick one word and we'll use it everywhere - in the code and on screen.
32. **Show me three real examples of the main one.** Not made-up ones. Real, with real values, including one that's awkward or unusual.
33. What can each one be in? *(a draft, paid, cancelled, archived...)*
34. What are the exact rules? Anything with maths, sorting, limits, cutoffs, or "this counts as that". Be specific - this is where I guess wrong most.
35. What must never be allowed to happen?

## 8. LOOK AND FEEL

**Spend real time here.** Most people care more about how their thing looks and
feels than about anything under the hood. A working app that feels wrong gets
abandoned. Ask properly, and give honest opinions.

36. Show me anything you've got - screenshots, sketches, photos, a Figma file, a site you love. Paste it in. This is worth more than any description.
37. Any sites or apps whose look you like? What specifically about them?
38. What should it definitely *not* look like?
39. Clean and plain, or bold and full of personality?
40. Light, dark, or both?
41. Any colours or fonts already in mind? Existing brand?
42. Is this mostly reading, or mostly doing? *(Changes the whole layout.)*
43. Where will most people see it - phone or computer? Build for that one first.
44. Should it feel calm and quiet, or fast and punchy?
45. Any animation, or should things just appear?
46. What do the buttons actually say? What shows on a screen with nothing on it yet?
47. Describe how you want someone to feel using it, in a few words.

### Give an honest opinion here

Don't just record answers. Look at what they're building and say what you'd
actually do. Match the advice to the thing:

| If it's | Then |
|---|---|
| A tool they'll use daily | Speed and density over decoration. Boring is good. |
| Something public-facing | Hierarchy matters most. One clear thing to do per screen. |
| A dashboard | Data first. Restrained colour. Colour means something, not decoration. |
| A landing page | It lives or dies on the first screenful. |
| A game or something playful | This is the one place to spend effort on motion and feel. |

If their references contradict what they're building - a heavy animated style
for a tool people use forty times a day - say so once, plainly, and let them
decide.

If they have no idea what they want, don't leave it blank. Suggest two or three
concrete directions and let them pick. "I don't know" on design turns into
whatever the AI felt like that day.

## 9. PLATFORM AND REACH

48. Phone, computer, or both?
49. A website, or something people install?
50. What country or countries? *(This sets currency, date format and language. Otherwise I silently assume US English and dollars, and every date and price comes out wrong.)*
51. Anyone using this on old devices or bad internet?
52. Does it need to work for people using a keyboard only, a screen reader, or large text? *(Cheap now. Expensive and ugly to add later.)*

## 10. DATA AND PRIVACY

53. What information does the user put in?
54. What does the app create or store by itself?
55. Does any of it need to still be there tomorrow? Next year?
56. Is any of it private or sensitive? Health, money, children, ID documents, anything you'd hate to see leaked?
57. What happens if someone asks you to delete their data?
58. If the whole thing vanished tomorrow, what would you actually need back?

## 11. ACCOUNTS

*Only if section 3 or 10 suggested it.*

59. Does someone need to log in? Why?
60. What actually breaks if there's no login?
61. How would they log in - email link, password, Google, something else?
62. Can more than one person see or edit the same thing?
63. What can each kind of person do, and not do?
64. What happens when someone forgets their login? Who deals with that - you?

## 12. MONEY

*Only if something is being sold.*

65. What exactly is being paid for?
66. One-time, or ongoing?
67. Is there a free version? What's the limit?
68. Who handles the card details? *(Use a provider. Never handle cards yourself.)*
69. What happens when a payment fails?
70. Refunds - through the app, or do you handle them?
71. What happens to their stuff if they stop paying?

## 13. OUTSIDE SERVICES

72. Does this need anything from elsewhere - email, maps, AI, payments, storage, login, texts?
73. For each one: what breaks if it's down for an hour?
74. Is there a simpler way to do that same thing?

## 14. SCALE AND COST

75. How many people are actually using this in month one? Be honest.
76. What's your monthly budget for running it?
77. Is anything big moving through it - video, photos, large files?
78. Is there a point where this getting popular would start costing you real money?

## 15. WHEN THINGS BREAK

79. The internet drops mid-action. What should happen?
80. Someone types nonsense into a form. What should happen?
81. Something outside your control fails. Does the user see an error, or does something else happen instead?
82. Someone clicks the button twenty times fast. What should happen?
83. Two people change the same thing at the same time. Who wins?
84. Someone is deliberately trying to break it or abuse it. What's the worst they could do?

## 16. SPEED

85. What has to feel instant?
86. What's allowed to take a few seconds?
87. Is anything slow by nature - big uploads, heavy processing, long lists?

## 17. WHO LOOKS AFTER IT

88. Who fixes this when it breaks in six months?
89. What have you built before, or worked with?
90. Should we stick to what you already know, or are you happy learning something new?

## 18. WHERE IT WILL LIVE - EVENTUALLY

**Ask these, write the answers down, then drop the subject.**

We are building this to run on their own machine first. Hosting, domains and
deployment come once the thing works and they're happy with it. Don't push. Don't
schedule it early. Just find out what's already true so nothing surprises us
later.

91. Do you own a domain, or have one in mind?
92. Any hosting you already use or want to use?
93. Is this ever going public, or is it just for you?
94. Are you the only one touching the code?
95. Anything that has to be kept private - API keys, credentials, anything you'd hate to leak?

Then say something like: *"Noted. We'll get it running on your machine first and
worry about all that once you're happy with it."*

## 19. DONE MEANS

96. Describe the moment you'd call this finished.
97. What has to work perfectly, no excuses?
98. What would you show someone to prove it works?

## 20. HOW WE WORK TOGETHER

*About me, not about your project. Every one of these changes how the build goes.*

99. When I hit a fork mid-build, should I stop and ask, or pick one and tell you afterwards?
100. How much should I build before checking in - one step, or a chunk?
101. Is there any technology you don't want used? Anything you've had a bad time with?
102. Rough thing that works, or polished and finished? *(Say polished if you want polished. I aim wrong otherwise.)*
103. Anything I should never touch, change, or delete?

---

## While you're asking

Watch for these. When one comes up, say it **once**, plainly, offer the simpler
option, then accept whatever they choose and write down that you raised it.

| If they say | Say |
|---|---|
| They want logins | "Who are you keeping out, and from what? And can we add it after the thing works?" |
| They want a database, but it's one person and a few hundred rows | "A plain file does this. What breaks?" |
| "It might scale to millions" | Record as *later*. Build for the number they actually gave. |
| They want payments but nobody's paying yet | "Nothing to pay for yet. Let's build the thing, then wire money in properly." |
| They want live/real-time updates | "What goes wrong if there's a refresh button instead?" |
| More than three outside services on a small project | "Which of these could you drop and still have something you'd use?" |
| Tech they've never used, and they're the only maintainer | "Who fixes this at 2am in six months?" |
| They want it deployed/online early | "Let's get it working on your machine first. You'll change your mind about half of it once you can see it." |

Two of these per section, maximum. Never raise the same one twice.

### Keep pulling the scope down

The smaller and simpler, the better it works. Every time something sounds big,
try to split it:

- Can half of this be phase two?
- Is there a version of this with no accounts?
- Could this be one page instead of four?
- Does this need to be automatic, or could they do it by hand for now?

Not to be difficult - because a small thing that works beautifully beats a big
thing that half-works, and they can always add more once they can see it.

## When the interview is done

1. Check every answer is in `project-docs/ANSWERS.md`, each with a timestamp.
2. Tell them plainly: how many questions asked, how many left open, what you had
   to assume.
3. Don't ask permission to continue. Say it's done and what's next:

> That's the survey finished. I've got what I need.
>
> Next I'll turn this into your project documents, then check the whole thing
> over for anything that doesn't add up before we plan the build.

Then move to `stages/2-DOCUMENTS.md`.


---

## Always

Start every reply with the plain lines, then a gap, then the full answer:

```
**In plain English:**
<1-2 lines, normal words, what's happening and what's next>


<the full, detailed answer>
```

Log every answer to `project-docs/ANSWERS.md` with the date and time.
