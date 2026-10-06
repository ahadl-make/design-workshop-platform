# UX & UI principles (for workshop prompts)

> Universal principles for framing and prototyping internal tools. Paste or @-mention with the ideate + build prompt. Not a design-system spec.

---

## Layout

### Visual hierarchy
- **Most important information** should be largest and most prominent
- Use **size, color, and spacing** to guide the eye
- **Headings** should be clearly larger than body text
- **Actions** (buttons) should stand out from content
- **One primary action** per view — don't compete with equally loud buttons

### Typography
- Clear hierarchy: one page title (H1), section headings, then body
- Body text readable at a glance — don't shrink labels to fit more chrome
- Labels on controls should be action-oriented ("Save changes", "Create template")

### Spacing & grouping
- **Group related items** together (proximity)
- **Whitespace** separates sections — don't cram everything together
- **Consistent spacing** (a simple scale: 4 / 8 / 16 / 24 / 32px)
- **Padding inside containers** comfortable (16px minimum)

### Alignment
- Align to a grid or consistent margins
- Left-align text (easier to scan than centered blocks of copy)
- Consistent margins on all sides

---

## Interaction patterns

### Buttons
- **Primary** — prominent (larger, filled, clear label)
- **Secondary** — quieter (outline or ghost)
- **Destructive** — clearly different (warning / danger style)
- **Disabled** — visually distinct and not clickable-looking

### Forms & inputs
- Labels above or beside inputs (not only as placeholders)
- Required fields marked
- Error and success states clear and specific
- Validation when it helps — don't leave people guessing what went wrong

### Navigation
- Current location clear (highlight, breadcrumbs, or page title)
- Next step obvious
- A way back / cancel when the maker might want to leave

---

## Content & communication

### Errors
- Plain language (not stack traces as the only message)
- Suggest what to do next
- Offer recovery (retry, fix, get help)

### Success
- Confirm what happened ("Environment ready" not just "OK")
- Point to the next step if there is one
- Keep it brief

### Empty states
- Explain why it's empty
- Suggest the first useful action
- Prefer a helpful empty state over a blank panel

---

## Nielsen's 10 usability heuristics

Use as a quick checklist when reviewing a prototype. [Source: NN/g](https://www.nngroup.com/articles/ten-usability-heuristics/)

1. **Visibility of system status** — show loading, progress, confirmations
2. **Match between system and real world** — language the maker already uses
3. **User control and freedom** — exits, undo, cancel
4. **Consistency and standards** — follow the conventions of *this* tool (Backstage, the vibe-coded app, etc.)
5. **Error prevention** — good defaults, confirmations, constraints
6. **Recognition rather than recall** — options visible; don't rely on tribal memory
7. **Flexibility and efficiency of use** — shortcuts and smart defaults for frequent users
8. **Aesthetic and minimalist design** — every element earns its place
9. **Help users recognize, diagnose, and recover from errors** — plain messages + next steps
10. **Help and documentation** — searchable, short, task-focused when needed

---

## Prototyping rules for this workshop

- **One screen, one moment** — happy path first
- **Rough and clear beats pretty** — hierarchy and a primary action matter more than polish
- **Use the design system** — build with Backstage UI (BUI) components from `bui.md`, colours only via `--bui-*` tokens. Don't invent, re-use. Missing a component? Note it — that's a conversation with the platform team, not a hand-rolled button
- **Match the surface you own** — use the screenshots in `_context/assets/` as the layout anchor; don't invent a generic SaaS dashboard
- **Show feedback** — loading, success, or error for the one interaction you wire
- **Don't invent evidence or copy** — placeholder labels are fine; fake DX quotes are not

### Common mistakes
- Too much information on one screen
- Unclear primary action
- No feedback after a click
- Jargon the non-engineer maker won't know
- Tiny click targets / poor contrast
- Building before the direction is agreed
