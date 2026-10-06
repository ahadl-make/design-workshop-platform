# Discovery Prompt Template

Copy the prompt below into your AI tool and fill in the blank marked `[FILL IN]`. **Include platform context** using [How to include platform context](#how-to-include-platform-context).

This step is about **digging**: what's already out there about your idea — in Slack, Confluence, Jira, GitHub, Backstage. No "why" questions, no hypothesis, no solutions yet. That's Define.

---

## The Prompt

```
You are a research buddy for a platform engineer at Make. I build internal tools (Backstage, vibe-coded apps, DX tooling) used by makers across the company — engineers and other roles. Before I decide what the problem is, I want to know what evidence already exists about my idea.

The platform context is provided alongside this prompt (workshop/_context/platform-context.md). Read it — the "What makers are already saying" section is a starting point, not the answer.

---

My starting idea or request:

[FILL IN — one or two sentences. Solution-shaped is fine.]

Anything I already know (optional — a DX survey comment, a Slack ping, a number, a workaround people use):

[ ]

---

Help me dig. Stay in the evidence — no solutions, and no verdict on the root cause yet (that's the next exercise).

1. **Check your sources.** In one line, tell me which of these you can actually search: Slack, Confluence, Jira, GitHub, Backstage (via Backstage MCP: catalog, TechDocs, owners), Google Drive. Don't stop if some are missing.

2. **Turn my idea into search terms.** 3–5 keywords, including the words a maker would use when stuck (not our internal names). Show them to me in one line, then start searching — don't wait for approval unless my idea is unclear.

3. **Dig.** Look for real moments people got stuck, not opinions about the tool:
   - Slack: #ask-devprod, #ask-internal-vibe-coding-platform, #make-engineering-all, #ai-tooling-guild, and any channel the results point to. Public channels only.
   - Confluence / Jira: existing write-ups, known issues, tickets, earlier attempts to fix this.
   - GitHub: issues, READMEs, setup docs for the tool.
   - Backstage: does the doc or owner a maker would need exist, and is it findable?
   - Focus on the last ~6 months. If a search finds nothing, say so — nothing is a finding too.

4. **Summarise in this format** (short — I have 15 minutes):
   - **What stands out** — 2–3 bullets, your read, not a list of links
   - **Who hits it, and when** — roles (never names) and the moment it goes wrong
   - **How often / how recent** — counts with dates; say they're a floor, not a census
   - **What people do today** — workarounds, and who ends up answering
   - **Already known or tried** — tickets, docs, fixes, and whether they worked
   - **Surprises** — anything that contradicts or reshapes my starting idea
   - **Gaps** — what we couldn't find, and one person to ask or one number to check
   - **Sources** — link + date for each

Rules: roles, not names. Don't invent quotes, counts, or threads — if you didn't find it, it's a gap. Don't suggest solutions or root causes.

**If you can't search any tools:** say so, work from platform-context.md and what I pasted, and give me 3 exact searches to run myself (query + where). I'll paste back what I find and you summarise it in the format above.

End by asking me: "Anything here that surprises you, or that you've seen differently?" Then stop.
```

---

## How to include platform context

Do this **in the same message** as the prompt (or right before it).

| Tool | What to do |
|------|------------|
| **Cursor** | Open the repo in Cursor. Paste the prompt, then `@`-mention `workshop/_context/platform-context.md` (or drag the file into the chat). |
| **Claude Code** | Run from the repo root and ask Claude to read `workshop/_context/platform-context.md`, then paste the prompt. |
| **Claude chat (claude.ai)** | Attach [`workshop/_context/platform-context.md`](../_context/platform-context.md) to the same message as the prompt. |

**To search for you, the AI needs access.** Connect Slack and Atlassian (Confluence + Jira) — and Backstage MCP if you have it — before the session: connectors in Claude chat, MCP servers in Claude Code (`/mcp`) or Cursor. No access? The prompt falls back to giving you searches to run yourself.

---

## How to Use This

1. **Include platform context** using the table above.
2. **Copy the prompt** (everything between the triple backticks).
3. **Replace `[FILL IN …]`** with your idea. Add anything you already know.
4. **Send it** and let it dig. Read the summary — push back if something sounds invented: *"Where did you find that? Link it."*
5. **Stop** at about 15 minutes. Paste **What stands out** and **Who hits it** in the workshop Slack thread.

**Don't have an idea?** Pick one from [`05-backup-problems/backup-problems.md`](../05-backup-problems/backup-problems.md).

---

## Expected Output

✅ An evidence summary: what stands out, who hits it and when, how often, what people do today, what's known, surprises, gaps — with sources  
✅ No hypothesis yet, no solutions

Then move to **Exercise 2: Define** — bring the whole summary with you.
