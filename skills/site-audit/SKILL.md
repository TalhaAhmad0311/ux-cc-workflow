---
name: site-audit
description: The team's standard UX/UI audit of an existing site, page or Figma file, before any redesign. Use when an order says "audit", "review the current site/page", "what's wrong with", or a project starts with understanding what exists. Covers capture, measuring, findings, severity and the report format. Has a normal and a deep mode.
---

# Site audit

How this team audits what exists. The project's own `CLAUDE.md`, briefs and `project-rules.md` decide priorities, scope
and risk; this skill decides the method. Where they disagree, the project wins.

## Pick the depth first
- **Normal** (default): the pages in the order, at 1440 and 375, one report.
- **Deep**: when the user says "go deep" / "in detail", the project's `CLAUDE.md` says the project is high-risk or
  client-facing at launch, or the order covers a whole site. Adds 768, every state, a second review pass (below),
  and competitor research if the order allows.
State the depth in the report's first line.

## Limits (always)
- Audit only: no designs, no new features, no fixes.
- Read only: no passwords, no form submits. Decline non-essential cookies (note first what the banner hides).
- Scope is UI/UX unless the order says otherwise. Speed, SEO and code are out unless asked.
- Quote the user's words when the order narrows scope.

## Steps
1. **List what exists**: every page or flow in scope, plus the Figma file's pages, frames, styles and components
   (note "empty" if so). Write "not reachable / needs login" rather than guessing.
2. **Capture** at the widths for your depth (1440×900, 375×812; deep adds 768×1024). Open menus and hover states by
   hand. Full-page shots where length matters. Timed shots for animations (`-after-1s`, `-3s`).
3. **Measure, don't eyeball**: contrast ratios, tap targets in px (44 px minimum), real link destinations (URL or "#"),
   page length. Count things ("8 cards", "45 links"), never "several".
4. **Check facts** on the live page and in its source (e.g. meta text against body text).
5. **Write findings**, then "Not checked", then "Questions for the user". Questions the Lead can settle are answered
   as "Decisions" and not sent up.
6. **Deep only: second pass** as its own step. A UX review against Nielsen's 10 heuristics (H1–H10) plus a visual
   review (hierarchy, CTAs, consistency, form errors, wayfinding, phone ergonomics, type, colour, spacing, imagery,
   "premium for its price"). Refer to audit findings rather than repeating them.
7. **Deep only: competitor research** if allowed: 12–15 sites, URL and date cited, patterns only, never copied.

## Evidence
- Folder: `team/notes/audit/` (or the order's folder).
- Names: `<page>-<width>.png` (`menu-open-375.png`). Annotated copies add `-annotated`: numbered callouts in one colour
  that stands out from the site, readable at normal zoom.
- Note capture limits ("Chromium with an iPhone profile, not Safari", "saved at 792 px wide").

## Severity
- **High**: likely stops or loses the main conversion.
- **Medium**: slows or confuses, or noticeably hurts trust.
- **Low**: polish.
The user's own confusion about the structure counts as a real finding.

## Report (team version): `team/notes/audit-<name>.md`
- First line: scope, depth, and "How it was checked" (live, logged out, widths, read only, what was measured).
- §1 What's in Figma
- §2 The page today: sections top to bottom, screenshot links per width
- §3 Problems table: `# | Severity | Where | What's wrong | Why it matters | Seen in`, sorted High → Low
- Top problems (ranked), then "How a redesign would answer them"
- Not checked
- Questions for the user (one at a time when asked)
- For later

## Client version (only when the order asks for something to send)
The client wants plain words, not the team report:
- One section per screen, plain sentences.
- No severity scale, no heuristic names, no jargon. Mark only "Important" items.
- Each point: the problem, then "We will…" (the direction, not the exact how).

## Before reporting
- Every finding has a screenshot or a measurement.
- Nothing invented. Anything unverified sits under "Not checked".
- Report up in one line plus the file path.
