---
name: design-review
description: The team's standard review of design work by the Lead (critique) or the Product Design Manager (review): what to check, severity, widths, pass/fail and the written format. Use when reviewing a designer's frames, directions, a build-out or fixes before they go up the chain. Has a normal and a deep mode.
---

# Design review

How the reviewer checks design work before it goes up. Run `design:design-critique` for the expert pass; this skill
adds the team's own checks and format. The project's `CLAUDE.md` and `project-rules.md` decide what matters most.

## Pick the depth first
- **Normal** (default): the changed frames, at 1440 and 375, one round.
- **Deep**: when the user says "go deep", the project is high-risk, or it's a final before the user or a release.
  Adds 768 (and any widths the project lists), every state, stress cases, and an independent pixel or node check
  of your own ("checked by me, not only the designer").

## Always check
- **Scope:** nothing outside the order changed. Where possible, snapshot before work and compare ids, positions and
  sizes after ("Desktop byte-identical").
- **Fidelity:** the user's picks and own edits are kept, never overwritten.
- **Content:** real, matched to the source item by item ("7 specs × 4 models"). No invented facts or claims the
  product can't support. No placeholder tags.
- **Audit items:** still answered.
- **Contrast:** AA, measured at the worst pixel. **Tap targets:** 44 px or more. Body text 16 px or more on phone.
- **Hover-only actions:** none that touch users can't reach.
- **Consistency:** the same component looks and behaves the same everywhere.
- **Directions:** clearly different in structure, not just colour.
- **Images:** faces or subjects not covered by UI; nothing lost after import.
- **Hidden content:** scrolled or collapsed cells checked on their own.
- **Copyable text** (emails, numbers) reads correctly; nothing clipped.
- **Scope creep:** anything new goes up as a question, not into the design.

## Severity
🔴 Critical (blocks the pick or breaks the page) · 🟡 Moderate (fix before it goes up) · 🟢 Minor (polish; can wait)

## Lead critique format: `team/notes/<order>-critique-ux-lead.md`
- Header: what was viewed (frame ids, 1:1 slices), widths, depth, and what was not re-measured.
- Overall impression
- Usability: `Finding | Severity | Recommendation`
- Visual hierarchy: where the eye goes, per direction
- Consistency: `Element | Issue | Recommendation`
- Accessibility
- What works well
- Priority fixes (numbered, for the designer)
- `## Round N re-check` sections appended, never a new file

## PDM review format: `team/notes/<order>-review-pdm.md`
Verdict ("approved after one small fix") · Fixes · Flags decided · Checked · Not checked · context or handoff note ·
"Fix re-check: passed".

## Pass / fail
- **Pass:** no 🔴, no open 🟡, scope clean, content matched.
- **Fail:** back to the designer with the numbered fixes. Re-check only what changed.
- Untested widths or states go under "Not checked"; never report them as passed.
- Questions you can settle yourself are decided, not sent up.

Report up in one line plus the file path.
