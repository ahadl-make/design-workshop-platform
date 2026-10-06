# Platform Design Workshop

A 3-hour facilitated design thinking workshop for **Make platform engineers**. You'll work through a real idea or request — your own or a provided one — using a structured process: discover the maker's problem, define goals, explore a direction with an AI design buddy, prototype one moment, test it with a peer, and improve it.

**Design the seats, not the engine.** Today is about how makers *use* what you build — not how the infrastructure behind it works.

No design background needed. Bring a laptop.

**FigJam board:** [Design workshop – platform ✨](https://www.figma.com/board/okSLEZfQZO8ecbwHYyhl2w/Design-workshop-%E2%80%93-platform-%E2%9C%A8?node-id=0-1&t=Zpoe5N1cntLMMYFU-1)

---

## What you'll do

| Block | Time | What happens |
|---|---|---|
| Welcome | 8 min | Name + one-sentence idea |
| Theory walk (FigJam) | 15 min | What design is, the car, double diamond |
| **Two Briefs** | 20 min | Feel why a problem brief beats a solution brief |
| Break | 10 min | |
| **1. Discovery** | 15 min | Use AI to turn your idea into a needs hypothesis |
| Checkpoint | 5 min | Paste the hypothesis in Slack |
| **2. Define** | 15 min | Goal, success sentence, moment to prototype — still no screens |
| **3. Ideate + Prototype** | 55 min | Explore directions — then build one rough moment |
| **4. Pair Test + Improve** | 20 min | Test with a partner, change one thing |
| Close | 12 min | Share + commitment |

---

## Before the workshop

1. **Clone or download this repo** — you'll need the files during the session
2. **Have your AI tool ready** — Claude, Cursor, V0, or ChatGPT all work
3. **Bring an idea** — one sentence: the idea or request, and who you think it's for. If you don't have one, we have backup problems ready (real DX themes).

---

## Folder structure

```
workshop/
├── _context/
│   ├── platform-context.md             ← Makers, evidence, how to think
│   ├── ux-principles.md                ← Hierarchy, heuristics, prototype rules
│   ├── platform-surfaces.md            ← Backstage surface anatomy
│   ├── bui.md                          ← Backstage UI (BUI) — the design system you build with
│   ├── bui-starter.html                ← Starting file for your prototype (BUI + Make purple)
│   └── assets/                         ← Backstage screenshots
│
├── 01-exercise-discovery/
│   ├── task-card.md
│   └── prompt-template.md
│
├── 02-exercise-define/
│   ├── task-card.md
│   └── prompt-template.md
│
├── 03-exercise-ideate-prototype/
│   ├── task-card.md
│   └── prompt-template.md
│
├── 04-exercise-pair-testing/
│   ├── task-card.md
│   └── prompt-template.md
│
└── 05-backup-problems/
    └── backup-problems.md
```

---

## How the hands-on arc works

Three AI conversations, with walls between them, then a test:

1. **Discovery** — one needs hypothesis: who struggles, with what, and why. No solutions.
2. **Define** — three lines: goal, *"We'd know this worked if [a maker did this],"* and the moment to prototype. No layouts.
3. **Ideate + Prototype** — 2–3 different directions described as what the maker sees and does, pick one, approve a short plan, then a rough prototype built from Backstage UI (BUI) components, with everything faked behind the screen. No code until the plan is approved.
4. **Test + Improve** — a partner plays the maker and tries your success sentence; you change the one thing they stumbled on.

If the AI jumps to building early, stop it: *"Go back. No code until I approve the plan."*

Include [`workshop/_context/platform-context.md`](workshop/_context/platform-context.md) with Discovery and Define. For Ideate + Prototype, also include `ux-principles.md`, `platform-surfaces.md`, `bui.md`, `bui-starter.html`, and the matching screenshot from `assets/`. See each `prompt-template.md` for Cursor / Claude Code / paste instructions.

---

## After the workshop

- Your needs hypothesis goes in the Slack thread at the checkpoint. Before you leave, add your success sentence and what you changed after testing
- Show your moment to **one real maker of that role** this week
- Reuse the prompts anytime you get a solution-shaped ping or a DX comment you want to turn into a brief
