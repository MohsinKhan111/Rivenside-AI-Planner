# Rivenside AI Planner

Instructions that make an AI coding tool plan your project properly before it writes any code.

It is just text files. Nothing to install, no account, no API key.

## Why

AI forgets. Every message it starts again from a shorter summary of your project. It acts like it remembers everything, so you assume it does.

That is why projects fall apart halfway. You ask for a new feature in week three. The AI cannot re-read the whole project, so it patches the part it can see and tells you it works. It usually does work. The app is also slower and messier now, and you will not notice for weeks.

The fix is not a better memory. It is not needing one. Answer everything up front, write it down, break the build into steps small enough that each one is obvious on its own.

## What it does

1. Asks you questions, one at a time. Around 30 for something small, more for something serious.
2. Writes down every answer as you go.
3. Reads it all back, checks it like an engineer would, and asks about anything that does not add up.
4. Turns it into a build plan of small steps, then builds them in order.

It keeps everything on your own machine until you are happy with it. No hosting, no domains. Logins and payments are saved for later, after the thing actually works.

## What you need

Claude Code, Cursor, or a similar AI coding tool. A Claude subscription if you use Claude Code.

## Setup on a Mac

**1. Open Terminal.** Press Command and Space, type `Terminal`, press Enter.

**2. Install Claude Code.** Paste this and press Enter:

```
curl -fsSL https://claude.ai/install.sh | bash
```

**3. Download Rivenside.** Click the green Code button at the top of this page, then Download ZIP. Open the downloaded file to unzip it. You will get a folder called `Rivenside-AI-Planner-main`. Rename it to `rivenside` so the commands below are shorter.

**4. Make a folder for your project.** Anywhere you like. Call it whatever your project is called.

**5. Drag the unzipped `rivenside` folder into your project folder.**

**6. Point Terminal at your project.** Type `cd ` (with a space after it), then drag your project folder onto the Terminal window and press Enter.

**7. Start Claude.** Type:

```
claude
```

The first time, it will ask you to log in through your browser.

**8. Start the interview.** Type this and press Enter:

```
Read rivenside/START-HERE.md and begin
```

That is it. Answer the questions.

## While you are answering

Take your time. It saves everything as it goes, so you can close the laptop and come back later.

If a question stumps you, say `skip`, `I don't know`, or `you decide`. It will note it and move on. Guessing an answer is worse than skipping one, because guesses get written down as facts.

Paste in anything that helps. Screenshots, links to sites you like, sketches, half-finished notes.

## What you end up with

A folder called `project-docs` in your project, containing:

| File | What is in it |
|---|---|
| `RULES.md` | The limits you agreed. Short. Read at the start of every session. |
| `PROJECT.md` | What it is, who it is for, what it will never do |
| `FEATURES.md` | Every feature, numbered, marked required or later or no |
| `DATA.md` | What things are called, real examples, the exact rules |
| `DESIGN.md` | How it should look and feel |
| `DECISIONS.md` | Why each choice was made, dated |
| `OPEN.md` | Anything still unknown |
| `AUDIT.md` | The engineering check before building |
| `BUILD-PLAN.md` | The steps, grouped into phases |
| `PROGRESS.md` | Which step you are on |

Plain markdown. Any AI tool or any person can read them.

## Using it on a project that already exists

Same steps. It reads your code first, writes down what the code actually does, and only asks you about things the code cannot tell it. If your answers and the code disagree, it says so rather than picking one.

## Changing it

Everything is a text file. If a question is wrong or missing, open `rivenside/stages/1-INTERVIEW.md` and edit it.

## Licence

MIT. Do what you like with it.
