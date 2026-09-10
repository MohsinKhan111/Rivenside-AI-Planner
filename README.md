# Rivenside AI Planner

An AI project planner that interviews you, documents your project, checks for gaps and contradictions, and creates a build plan before coding begins.

Just text files. Nothing to install, no account, no API key.

One important note: this is for documentation and planning only. It doesn’t write any code. It gives you a clear foundation and mental map of what you’re building, how it fits together, and how ambitious or technically deep it is. You still need to review your code and architecture carefully and build responsibly. It won’t solve those problems for you, but it can help you think about them from the start.

## Why

Starting a project with AI usually means explaining your idea, scope, requirements, and decisions yourself, prompt by prompt. Then you have to keep repeating and maintaining that context as the project grows.

This flips that process around. The AI interviews you, asks the questions, records the answers, cross-checks everything for gaps and contradictions, and organizes it into proper project documentation before you start coding.

You review that foundation first, then build from it in small, clearly defined steps.

## What it does

1. Asks you questions, one at a time. Around 30 for something small.
2. Writes down every answer as you go.
3. Reads it all back, checks it like an engineer would, asks about anything that does not add up.
4. Turns it into a build plan of small steps, then builds them in order.

Everything stays on your own computer until you are happy with it. No hosting, no domains. Logins and payments come later, after the thing actually works.

---

# Setup

You need **VS Code**, **Claude Code**, and a **Claude subscription**.

Same steps on Mac and Windows.

### 1. Install VS Code

Download and install [Visual Studio Code](https://code.visualstudio.com/) if you don't already have it.

### 2. Install Claude Code

Open VS Code.

Go to **Extensions** on the left side and search for:

**Claude Code**

Install the official Claude Code extension.

Once installed, open Claude Code from VS Code and sign in with your Claude account.

### 3. Download the Planner

Download this repository from GitHub:

**Code -> Download ZIP**

Extract the ZIP file.

Rename the folder to:

`Rivenside-AI-Planner`

### 4. Create your project

Create a new folder for whatever you want to build.

For example:

`My Game`

Then put the `Rivenside-AI-Planner` folder inside it.

Your project should look like this:

```text
My Game/
└── Rivenside-AI-Planner/
```

### 5. Open your project in VS Code

In VS Code, go to:

**File -> Open Folder**

Select your project folder (`My Game`).

### 6. Start the Planner

Open Claude Code inside VS Code.

Tell it:

```text
Read Rivenside-AI-Planner/START-HERE.md and begin
```

Claude will read the Planner and guide you through the rest.

That's it. You don't need to install anything else for the Planner itself.

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

This is built for starting from scratch. An empty folder, an idea, nothing written yet. That is where it does its best work.

You can still use it on a project that already exists. It reads your code first, writes down what the code actually does, then only asks about things the code cannot tell it. If your answers and the code disagree, it says so instead of picking one. Just know that is the rarer case, not the main one.

## Changing it for yourself

Once you download it, your copy is yours. Edit anything.

Questions wrong or missing? Open `Rivenside-AI-Planner/stages/1-INTERVIEW.md` on your computer and change them. Nothing you do affects anyone else.

## Licence

MIT. Do what you like with it.
