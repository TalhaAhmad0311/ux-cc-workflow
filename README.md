# ux-cc-workflow

A ready-to-use team setup for running UX and design work with **Claude Code** (desktop app, Code tab).

You talk to one lead session, the **Head of Product**. It plays PM, design manager and lead, and runs short-lived
sub-agents for the hands-on work: audits, redesigns, reviews, QA. A **Personal Assistant** session handles outside
tools such as Jira, calendar, docs and mail. Everything the team knows lives in plain files, so work survives long
chats and handovers.

It holds no project content. The first session asks you about your product and fills it in.

## What's inside

| Path | What it is |
|---|---|
| `START-HERE.md` | Step-by-step setup (about 10 minutes) |
| `CLAUDE.md` | How the product is run; the Product section is filled in at setup |
| `team/START.md` | The Head of Product's setup steps |
| `team/ORG-CHART.md` | How work is split into sub-agents, files, quality, release and succession |
| `team/WORKING-PREFERENCES.md` | How you like to work; every session follows it (edit to taste) |
| `team/HANDOVER-TEMPLATE.md` | Used when a session retires and hands over |
| `team/QA-DEFINITION-OF-DONE-TEMPLATE.md` | The release bar, filled in per product |
| `assistant/CLAUDE.md` | The Personal Assistant's rules |
| `skills/` | Four team skills: `project-kickoff`, `site-audit`, `page-redesign`, `design-review` |

## Quick start

1. Click **Use this template** (or download the ZIP) and put the files in your product folder.
2. Install the skills so every session can use them:

   ```bash
   cp -R skills/* ~/.claude/skills/
   ```

3. Open the folder in the Claude desktop app, Code tab, and start a new session on Opus.
4. Type: **"You are the Head of Product. Follow team/START.md."**
5. Answer its questions one at a time. It sets up the sidebar, starts the Personal Assistant and tells you when it's
   ready.

Full details, including what to do if your folder already has a `CLAUDE.md`, are in [START-HERE.md](START-HERE.md).

## How it works

- **One lead, many short-lived helpers.** The Head of Product splits each job into small pieces and runs sub-agents
  for them, in waves. Helpers finish and disappear; only the lead stays in your sidebar.
- **Work in files, not chat.** Each job gets its own folder in `team/work/` with a brief and a report, so nothing is
  lost when a chat gets long.
- **Quality before release.** Nothing ships until a QA pass checks it at desktop, tablet and phone widths.
- **Succession.** When the lead's chat gets long (about 300K tokens), it writes a handover, starts its successor and
  stays on as an "Advisor" you can ask about history.
- **You stay in charge.** Anything outward-facing (pushes, deploys, messages to people) waits for your yes.

## Requirements

- The Claude desktop app with the Code tab (the team uses its session tools: starting sessions, sidebar groups,
  pins, messages between sessions).
- Optional: connectors for Jira, Google Calendar, Docs, Drive or Gmail, for the Personal Assistant.

## Licence

MIT. See [LICENSE](LICENSE).
