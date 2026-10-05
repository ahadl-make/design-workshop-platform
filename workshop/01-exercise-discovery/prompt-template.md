# Discovery Prompt Template

Copy the prompt below into your AI tool and fill in the blank marked `[FILL IN]`. **Include platform context** using [How to include platform context](#how-to-include-platform-context).

---

## The Prompt

```
I'm a platform engineer at Make. I build internal tools (Backstage, vibe-coded apps, DX tooling) used by makers across the company — engineers and other roles. I want to understand the real problem behind an idea before I jump to a solution.

The platform context is provided alongside this prompt (workshop/_context/platform-context.md). Read it and use it as you ask questions.

---

My starting idea or request:

[FILL IN — one or two sentences. Solution-shaped is fine.]

Anything I already know (optional — a DX survey comment, a Slack ping, a number, a workaround people use):

[ ]

---

Help me dig into this — stay in the problem space, no solutions yet:

1. **Ask me "why" questions** to find the cause behind my idea. Two or three is enough — stop once we reach something a platform change could actually touch. Don't just accept my first statement. I'm a backend-minded engineer: if I drift into how the system works internally, pull me back to what the person experiences.

2. **Help me name who is affected and when:**
   - A specific role, not "users" (e.g. a designer, a new engineer, a tech lead).
   - What they are trying to get done, and the moment it goes wrong.

3. **Help me write a needs hypothesis:**
   - We think [ROLE] struggles with [PROBLEM] because [ROOT CAUSE].
   - They need [OUTCOME] without [CURRENT FRICTION].
   Keep it about what they need, not what we should build. The root cause can be technical, but the need must be written from the person's moment — what they see, wait for, or can't do — not from the system's point of view.

4. **One thing to check after today** (optional): one person to talk to or one number to look at that would tell me if the hypothesis is right. Don't invent evidence — if I don't know something, say it's a gap.

Be conversational. Ask one question at a time. We have about 15 minutes, so once the hypothesis is solid, stop.

Start by asking me: "Tell me more about [my idea]. Why do you think this is happening?"
```

---

## How to include platform context

Do this **in the same message** as the prompt (or right before it).

| Tool | What to do |
|------|------------|
| **Cursor** | Open the repo in Cursor. Paste the prompt, then `@`-mention `workshop/_context/platform-context.md` (or drag the file into the chat). |
| **Claude Code** | Run from the repo root and ask Claude to read `workshop/_context/platform-context.md`, then paste the prompt. |
| **V0 / ChatGPT / other chat** | Open [`workshop/_context/platform-context.md`](../_context/platform-context.md), copy its full contents, and paste **above** the prompt. |

---

## How to Use This

1. **Include platform context** using the table above.
2. **Copy the prompt** (everything between the triple backticks).
3. **Replace `[FILL IN …]`** with your idea. Add anything you already know.
4. **Send it** and answer the AI's questions honestly.
5. **Stop** when the hypothesis is solid (about 15 minutes). Paste it in the workshop Slack thread.

**Don't have an idea?** Pick one from [`05-backup-problems/backup-problems.md`](../05-backup-problems/backup-problems.md).

---

## Expected Output

✅ A needs hypothesis: "We think [ROLE] struggles with [PROBLEM] because [ROOT CAUSE]. They need [OUTCOME] without [CURRENT FRICTION]."  
✅ (Optional) One thing to check after today

Then move to **Exercise 2: Define**.
