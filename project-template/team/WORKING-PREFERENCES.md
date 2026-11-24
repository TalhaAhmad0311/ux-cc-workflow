# How the user likes to work (every session follows this)

## Talking to the user (the Manager and the Chief of Design do this; sub-agents report to the Manager in files)
- Short, clear updates, one step at a time. Plain words, no jargon.
- **One question at a time.** Put the recommended option first, and give buttons where the app offers them.
- Never ask about something the user has already decided, or something a session can settle itself.
- Quote the user's exact words when passing an order or an approval into a brief.
- When a command is for the user to run, paste the **full** command and say exactly where it runs (which
  project, terminal or branch). Never `!` in commands for web terminals.

## Decisions and approvals
- Confirm before anything outward-facing: pushes, deploys, publishing, messages to other people.
- **Standing permissions:**
  - the Chief of Design decides successions for Managers;
  - "do whatever necessary, let me know if you need permissions": act within your role, ask only for a real block.
- Follow the spec as final. Don't invent features, pages or "what ifs". Flag new scope to the user instead.
- Where copy isn't written, write a short, neutral, finished-sounding line. Never use `[Placeholder]` tags.

## Design choices
- When a visual choice is open, build 2–3 live variants behind a temporary switch (or a live tuner) and let the user
  compare. Don't guess or describe the options in text. Remove the switch once they pick.
- Keep the established look. Restyles that change the feel get rejected. Use the main brand colour sparingly.
- Compact but not tight; professional; calm, finished, product-like. Avoid over-formatting.

## Quality
- Verify before reporting, with screenshots and measurements, at several widths (desktop, tablet, phone). An
  automated "no overflow" check isn't enough: look.
- Report outcomes honestly: what was checked, what wasn't, what failed.
- After any sync or deploy, reload and confirm the change actually stuck.

## Team hygiene
- Edit only your own files. Never switch branches, stash or reset in the shared folder; other sessions have work there.
- Managers retire at a clean point at 300K context and become Advisors (see Succession in `ORG-CHART.md`).
- Keep `ORG-CHART.md` true: ids, titles and sidebar groups.
