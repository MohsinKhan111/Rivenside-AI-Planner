# Rivenside AI Planner

Makes an AI coding tool plan your project properly before it writes any code.

Just text files. Nothing to install, no account, no API key.

## Why

AI forgets. Every message it starts again from a shorter summary of your project, but it acts like it remembers everything.

So when you ask for a new feature in week three, it cannot re-read the whole project. It patches the part it can see and says it works. It usually does work. Your app is also slower and messier now, and you will not notice for weeks.

The fix is not a better memory. It is not needing one. Answer everything up front, write it down, then break the build into steps small enough that each one is obvious on its own.

## What it does

1. Asks you questions, one at a time. Around 30 for something small.
2. Writes down every answer as you go.
3. Reads it all back, checks it like an engineer would, asks about anything that does not add up.
4. Turns it into a build plan of small steps, then builds them in order.

Everything stays on your own computer until you are happy with it. No hosting, no domains. Logins and payments come later, after the thing actually works.

---

# Setup

You need [Claude Code](https://claude.com/product/claude-code) and a Claude subscription. Cursor and similar tools work too.

## On a Mac

**1.** Open Terminal. Press `Command` + `Space`, type `Terminal`, press Enter.

**2.** Install Claude Code. Paste this, press Enter:

```
curl -fsSL https://claude.ai/install.sh | bash
```

**3.** Download this repo. Green **Code** button above, then **Download ZIP**. Double click it to unzip. Rename the folder from `Rivenside-AI-Planner-main` to `Rivenside-AI-Planner`.

**4.** Make a folder for your project. Anywhere. Name it after your project.

**5.** Drag `Rivenside-AI-Planner` into your project folder.

**6.** In Terminal, type `cd` and a space, then drag your project folder onto the Terminal window. Press Enter.

**7.** Type `claude` and press Enter. First time, it opens your browser to log in.

**8.** Type this and press Enter:

```
Read Rivenside-AI-Planner/START-HERE.md and begin
```

## On Windows

**1.** Open PowerShell. Press the Windows key, type `powershell`, press Enter.

**2.** Install Claude Code. Paste this, press Enter:

```
irm https://claude.ai/install.ps1 | iex
```

Also install [Git for Windows](https://git-scm.com/downloads/win) if you do not have it. Claude works better with it.

**3.** Download this repo. Green **Code** button above, then **Download ZIP**. Right click the file, Extract All. Rename the folder from `Rivenside-AI-Planner-main` to `Rivenside-AI-Planner`.

**4.** Make a folder for your project. Anywhere. Name it after your project.

**5.** Drag `Rivenside-AI-Planner` into your project folder.

**6.** Open your project folder in File Explorer. Hold `Shift`, right click empty space, choose **Open in Terminal**.

**7.** Type `claude` and press Enter. First time, it opens your browser to log in.

**8.** Type this and press Enter:

```
Read Rivenside-AI-Planner/START-HERE.md and begin
```

---

## Answering the questions

Take your time. It saves as it goes, so you can close your laptop and come back later.

Stuck on one? Say `skip`, `I don't know`, or `you decide`. It notes it and moves on. Guessing is worse than skipping, because guesses get written down as facts.

Paste in anything that helps. Screenshots, links to sites you like, sketches, rough notes.

## What you get

A `project-docs` folder in your project:

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

## Already started your project?

Same steps. It reads your code first, writes down what the code actually does, then only asks about things the code cannot tell it. If your answers and the code disagree, it says so instead of picking one.

## Changing it for yourself

Once you download it, your copy is yours. Edit anything.

Questions wrong or missing? Open `Rivenside-AI-Planner/stages/1-INTERVIEW.md` on your computer and change them. Nothing you do affects anyone else.

## Licence

MIT. Do what you like with it.
