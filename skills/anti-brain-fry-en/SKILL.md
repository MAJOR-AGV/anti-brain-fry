---
name: anti-brain-fry-en
description: Against AI brain fry, the fried brain you get from overseeing AI agents all day. Ends every task with a card you can read in 5 seconds instead of a wall of text. A reminder of why the task was launched, what is done, and one single decision with two answers. For founders running several agents in parallel and for ADHD brains. Apply it at the end of every task, every time you deliver something, and every time you need the person's approval.
---

# Anti Brain Fry

The person reading you may have 10 agents open at the same time. When they come back to you, they have forgotten why they launched you. Every line they read costs them energy. Your end of task must read in 5 seconds and close in 1 click.

## The card

Your end-of-task report is this card. Nothing before, nothing after.

🎯 **Why you launched me:** [the starting goal in 1 sentence, framed as the benefit]

⚡ **What's done:** [the result in 1 or 2 sentences, from the person's side]

❓ **The one decision:** [a single closed question]

**[ 1: your recommendation ]**   |   **[ 2: the other option ]**

No intro, no list of steps, no code block.

## The rules

1. **Why = the benefit, not the technique.** "Stop losing sales when payment fails", not "fix webhook-handler.ts". If you know how long ago the task started, add it: "(2 h ago)".
2. **Done = what the person will see.** "Payment now retries 3 times on its own without blocking the customer", not "exponential backoff + events_log logger". If the task was a question, the answer goes here, in plain words.
3. **One single decision.** If you have several:
   - anything reversible that stays within the original request (reading, sorting, preparing a draft), you do it before handing back the card instead of offering it, and mention it in a few words under "What's done";
   - you only bring up the decision that is irreversible or commits the person: money, clients or customers, publishing, sending, deleting;
   - if several remain, ask the most blocking one. The others wait for the next card.
4. **Two answers, not three.** Option 1 is always your recommendation. Each answer says what will happen ("Yes, send the email"), never just "Yes".
5. **Nothing to decide?** Replace the ❓ line and the answers with: ✅ **Nothing to decide, it's closed.** If the next step is still waiting on someone or another agent, write instead: ⏳ **Nothing to decide, I'm waiting for [who or what].**
6. **Blocked?** The ❓ line says what you are missing, and the two answers are the two ways to unblock you.
7. **Zero jargon.** A technical term you can't avoid? Explain it in 3 words in brackets.
8. **Details live elsewhere.** Code, changed files, logs: a link or a file path, never pasted into the card. The person will ask if they want them.
9. **Their language.** Write in the person's language, card labels included (in French: « Pourquoi tu m'as lancé », « Ce qui est fait », « L'unique décision »).

## If your interface has real buttons

If you have a multiple-choice question tool (for example AskUserQuestion in Claude Code), ask the decision with that tool, your recommendation first. Keep the 🎯 and ⚡ lines in your message.

## Example

It's 4:30 pm. The person reopens a tab launched at 2 pm for a payment bug. In between, they handled 8 other topics.

**Before**

> I've finished analyzing `webhook-handler.ts` along with its dependencies in `/utils/retry.js`. Here are the changes: 1. I replaced the `while` loop with an exponential backoff system to avoid 429 errors on the API side. 2. I added an intermediate logger in the `events_log` table with a `pending_retry` status. 3. I changed the timeout from 5000 ms to 15000 ms. [...140 lines of code...] Which approach do you prefer for cache handling, and do you want me to run the unit tests on staging or update the database schema first?

Result: they have to reread everything to remember which project this is about, compare three technical options cold, then write a new message. They close the tab thinking "I'll deal with it later".

**After**

🎯 **Why you launched me (2 h ago):** stop losing sales when payment fails on the first try.

⚡ **What's done:** the system now retries automatically 3 times in the background, without blocking the customer.

❓ **The one decision:** if it still fails after 3 tries, should I email the customer a backup payment link?

**[ 1: Yes, send the email ]**   |   **[ 2: No, alert me on Slack ]**

Result: 4 seconds of reading. They type 1. The topic is closed.

## Before sending

- Does it read in 5 seconds?
- Can you tell why the task exists without rereading the history?
- One single question, closed, with two answers that say what will happen?
- No code block, no file name in the "Why"?
