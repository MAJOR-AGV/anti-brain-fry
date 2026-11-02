# Anti Brain Fry

[Version française](README.md)

**Every time your AI agent finishes a task, you get a 5-second card: why you launched it, what is done, one single decision.**

By Major. Free and open source.

You have 10 agents running. When one of them is done, you open the tab and hit a wall of text: changed files, 140 lines of code, three technical options and two questions. You no longer remember why you launched it. You close it thinking "later". By evening, your brain is fried: that's AI brain fry.

This skill turns the end of every task into a card. You type 1 or 2, it's closed.

## Before / after

It's 4:30 pm. You reopen a tab launched at 2 pm for a payment bug. In between, you handled 8 other topics.

**Before**

> I've finished analyzing `webhook-handler.ts` along with its dependencies in `/utils/retry.js`. Here are the changes: 1. I replaced the `while` loop with an exponential backoff system to avoid 429 errors on the API side. 2. I added an intermediate logger in the `events_log` table... [140 lines of code] Which approach do you prefer for cache handling, and do you want me to run the unit tests on staging or update the database schema first?

**After**

🎯 **Why you launched me (2 h ago):** stop losing sales when payment fails on the first try.

⚡ **What's done:** the system now retries automatically 3 times in the background, without blocking the customer.

❓ **The one decision:** if it still fails after 3 tries, should I email the customer a backup payment link?

**[ 1: Yes, send the email ]**   |   **[ 2: No, alert me on Slack ]**

4 seconds of reading. You type 1. The topic is closed.

## What the skill does

| | |
|---|---|
| **Puts you back in context** | One sentence on the why, framed as the benefit. No more rereading the history. |
| **Gives you the result** | What you will see, not how it was coded. |
| **One single decision** | The agent settles what is reversible on its own and only brings up what commits you: money, customer, publishing, deleting. |
| **Two answers** | The agent's recommendation as 1, the other option as 2. |
| **No wall of text** | Code, files and logs stay one link away, never pasted into your window. |

## Install

**Claude Code, Codex, Cursor and other agents (skills.sh)**

```bash
npx skills add MAJOR-AGV/anti-brain-fry --skill anti-brain-fry-en
```

**Hermes Agent**

```bash
hermes skills install MAJOR-AGV/anti-brain-fry/skills/anti-brain-fry-en
```

## Turn it on for every task

A skill runs when the agent judges it useful. To apply it at the end of every task, add this line to your `CLAUDE.md` (Claude Code) or your `AGENTS.md` (Codex, Cursor and others):

```
At the end of every task, apply the anti-brain-fry-en skill.
```

## About Major

Major (Anthony Gonnet Vandepoorte) builds and runs businesses with AI agents.

[YouTube](https://www.youtube.com/@major-agv) · [Instagram](https://www.instagram.com/major_agv) · [X](https://x.com/majoragv) · [LinkedIn](https://www.linkedin.com/in/anthonygonnetvandepoorte)

If this skill gave you back some energy, **star the repo**. It helps other founders find it.
