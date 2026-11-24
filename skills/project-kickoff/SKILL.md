---
name: project-kickoff
description: The team's standard start for a new project or a new phase: the questions to ask the user one at a time, and the background, goals and rules files they produce. Use when a Manager sets up a project (alongside team/START.md), or a project starts a new phase or client. Has a normal and a deep mode.
---

# Project kickoff

How the Manager learns what a project is, and writes it down so every role starts from the same facts. Follow
`team/START.md` for the team setup; this skill covers the questions and the files.

## Pick the depth first
- **Normal** (default): the core questions, one background file.
- **Deep**: when the user says "go deep", or the project is a full product, relaunch or new client. Adds the goals
  questions and a research plan before design starts.

## Ask the user (one question at a time, recommended option first, buttons where possible)
Core:
1. What the project is, and what "done" looks like for the current work.
2. Its areas, pages or modules.
3. Where the source of truth lives: specs, Figma, live site, repo.
4. What kind of work it is: design only, design + build, audit first?
5. How serious it is: personal, client, launch-critical. This sets the default depth for the skills.

Deep adds: goals (ranked), target audience, the one takeaway for a visitor, the next action you want them to take,
direction and personality, tone, feel, and visual references.

Never ask what the user already said or a role can settle itself. Never ask functional questions on a design-only
project.

## Files it produces
- **`CLAUDE.md` → Project section:** what it is, areas, source of truth, kind of work, **Default depth: normal/deep**.
- **`team/notes/project-background.md`:** Status · Links (final, earlier versions, live, competitors) · People and
  roles · History (dated) · Design stances to keep.
- **Deep: `team/notes/user-goals.md`:** a dated log of the user's own answers, quoted, each with a one-line reading,
  plus "Decision after step N" entries as they come.
- **`team/notes/project-rules.md`** (kept by the reviewer): the living rulebook, built only from quoted user decisions.

## Deep: research plan before design
`team/notes/plan-research-step-N.md`: Why this first · Covers · Method (desk only; evidence tagged strong / moderate /
thin) · Produces (a 5-minute readout) · Leads to (the one user decision) · Not in scope · Estimate.
Optional first-visitor tests with fresh task agents (5-second test, first-click questions); state that leaked context
is a limit.

## Done when
The Project section is filled in, the background file exists, the default depth is set, and the first order is
written as `team/notes/order-001-<name>.md` with the user's exact words.
