---
name: page-redesign
description: The team's standard process for redesigning a page or section, from order to final: briefs, 2–3 live directions, critique, the user's pick, build-out, cleanup and handoff. Use when an order says "redesign", "new design for", "give options for", or a page moves from audit to design. Has a normal and a deep mode.
---

# Page redesign

How this team takes a page from order to final. The project's `CLAUDE.md`, briefs and `project-rules.md` decide
priorities, look and risk; this skill decides the method. Where they disagree, the project wins.

## Pick the depth first
- **Normal** (default): 2–3 directions, one Lead critique, the user picks, build out.
- **Deep**: when the user says "go deep", the project is high-risk, or the page is the main conversion page. Adds
  research or benchmark first, 3–4 directions, stress tests with real extremes (e.g. 20 options, 73 variants, the
  longest name), PDM second opinion, multi-round critique and an independent pixel or node check.
State the depth in the brief.

## Before starting
- **Confirm the job:** a redesign (new structure) or a fix pass (same structure, cleaner)? Ask once if the order is
  unclear. A "recreation" when the user wanted a redesign is the most common rework.
- **Re-read the order file before every pass.** Later user orders often change the brief.
- **Read the user's own edits first** (Figma or code). Never overwrite them; ask "keep my change?".
- **Park old work**: rename it ("v1 (recreation)"), never delete.

## Briefs (PDM → Lead → Designer)
Each brief has: the user's exact words; read first; why; steps; rules; check before you report; notes file; limits
(own files and pages only); reporting (one line on start with an estimate, one line if blocked, one line when done).

## Directions
- 2–3 (deep: 3–4), side by side on a "Directions" page / TEMP section, or behind a `?v=a|b|c` switch in code.
- They must differ in **structure and hierarchy**, not just colour (squint test). Make the first screens clearly
  different from each other.
- Each gets a name and 2–3 lines on what it is optimised for; one-line comparison at the top.
- Desktop full page plus the top ~2 phone screens. All widths only after the pick.

## Rules for every direction
- Real content only. Never invent facts, numbers or features. Missing copy: a short neutral line, never a placeholder.
- Original images only, no screenshot crops.
- Every audit item stays answered; keep a mapping list in the notes.
- AA contrast for every text pair. Tap targets 44 px or more.
- Styles prefixed per direction (`A/Color/…`).
- A visual reference: copy the look, never the content. Add a "From the reference" list.
- Brand accent used sparingly. Calm, finished, professional. Word budget per screen; depth behind a click.

## Checks
1. **Designer self-check:** screenshot every frame at 1:1; alignment, clipping, contrast. Notes: idea, layout
   decisions, type, colour with contrast pairs, calls made.
2. **Lead critique** with the `design-review` skill. Fixes, then re-check rounds appended to the same file.
3. **Deep: PDM review**, a verdict plus fixes (some can wait for the build-out).

## The pick
- The team recommends one, with a fallback and the risks.
- The user chooses. Record the decision in `project-rules.md` with the user's words.
- **If the user rejects every option:** don't push a pick. Offer research, or polishing the closest direction.
- **If approval is withdrawn for one part:** reopen only that part.

## Build-out and close
1. The pick at every width, then a states sheet (hover, focus, open menus, empty, error), a components page and a
   tidy file (e.g. Page · Components · Archive).
2. **Remove the switch** in one step; list the leftovers to grep for.
3. **Handoff** with `design:design-handoff` into `team/notes/handoff/`, only when the user says development is on.
4. After a Figma import or capture, scan for blanks (lost images, icons, form fields).

## Variant report (to the PM, as a file)
What was added (links) · table of directions with "What each is like" · recommendation and fallback · screenshots
(including a second state) · how it was checked · flags · next step. The message up is one line plus the path.
