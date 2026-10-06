# Exercise 1: Discovery with AI
**Time:** 10 minutes  
**Goal:** Dig up what's already known about your idea — real moments people got stuck, who, how often, what they do today — before deciding what the problem is

---

## What You'll Do

1. **Open your AI tool** (Claude Code, Claude chat, or Cursor) — ideally with Slack and Atlassian connected

2. **Copy the prompt** from `prompt-template.md`

3. **Fill in:**
   - Your idea or request
   - Anything you already know (optional — a DX comment, a Slack ping, a number)
   - Include [`workshop/_context/platform-context.md`](../_context/platform-context.md) — see `prompt-template.md` for how

4. **Let the AI dig.** It searches Slack, Confluence, Jira, GitHub and Backstage, then summarises what it found. You read, question, and ask for links.

---

## Your Initial Idea

```
[YOUR IDEA OR REQUEST]
```

**Starting with a solution?** That's fine:
- "We should improve the Backstage docs search"
- "Devboxes idle too fast"
- "I want to add a template for cloud agents"

**Starting with a problem?** Also fine:
- "People still ask in Slack how to set up their environment"
- "Non-engineers bounce off our vibe-coded apps"

**Don't have an idea?** Grab a backup from `05-backup-problems/`.

**Feels too small?** Perfect. Small ideas still leave a trail in Slack — go find it.

---

## What "good" looks like

| Good | Not yet |
|---|---|
| Real threads and tickets, with dates and links | "Users find it confusing" with no source |
| Roles and moments ("a PM opening an app link from Slack") | Names, or "users" |
| "Searched Jira, found nothing" | Silence about where it didn't look |
| Something that surprised you | Only evidence that agrees with your idea |

**You have 10 minutes.** Keep it to ~5 searches. No "why" questions, no hypothesis, no solutions yet — that's Define. If the AI proposes a fix, stop it: *"Stay in the evidence."*

**AI can't search?** It gives you 3 searches to run yourself in Slack or Confluence. Run them, paste back what you find.

## Output

```
What stands out: …
Who hits it, and when: …
How often / how recent: …
What people do today: …
Already known or tried: …
Surprises: …
Gaps: …
Sources: …
```

---

## Next Step

Save the summary to `my-outputs/1-discovery.md`. Paste **What stands out** and **Who hits it** in the Slack thread. Then move to **Exercise 2: Define** with the full summary.
