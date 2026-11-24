# Product team kit: start here

This kit sets up one product to be run by **one Head of Product session** you talk to. It plays PM, managers and
Lead, and runs short-lived sub-agents for the hands-on work (many at once when a job splits). A Personal Assistant
handles outside tools. It holds no
product content: the first session asks you for that.

## What you need
- The **Claude desktop app** (Code tab). The team uses its session tools: starting sessions, sidebar groups, pins,
  messages between sessions.
- A folder for the product (your repo or an empty folder).

## Set it up (about 10 minutes)
1. **Copy** everything in this kit (`CLAUDE.md`, `START-HERE.md`, `team/`, `assistant/`) into the product folder.
   If the folder already has a `CLAUDE.md`, keep both: rename the kit's to `TEAM.md` and add the line
   `@TEAM.md` at the top of your own.
   Copy each folder in `skills/` (site-audit, page-redesign, design-review, project-kickoff) into `~/.claude/skills/`,
   so every session can use the team's skills.
2. **Open the folder** in the Claude desktop app, Code tab, and start a new session on **Opus**.
3. Type: **"You are the Head of Product. Follow team/START.md."**
4. **Answer its questions**, one at a time: the product's name, what it is, its areas, where specs and designs live,
   which disciplines the work needs.
5. It then pins itself, creates the Advisors group, starts the Personal Assistant, and tells you it's ready. From then on, talk to the **Head of Product** for product work, and to the **Personal Assistant** for
   Jira, calendar, docs and mail.

## What doesn't come with a copy (by nature)
- **Chat history and memory:** every session starts fresh; the files in `team/` are the team's memory.
- **Sidebar groups and pins:** the Head of Product recreates them during setup.
- **Tool sign-ins:** connect Jira, Google Calendar, Docs, Drive and Gmail (or your own tools) in the app's connector
  settings. The Personal Assistant tells you which are missing. Nobody types passwords or tokens for you.
- **Who's who:** session ids are filled in as the team is created.

## Day to day
- Ask the Head of Product for anything: "change X", "push", "where are we?". Its task list shows which jobs are running
  and roughly how long they will take.
- Say "push" to release; nothing ships before a QA agent passes it.
- The Head of Product retires itself when its chat gets long and stays as an "Advisor" for history.

## Files
| File | What it is |
|---|---|
| `CLAUDE.md` | How the product is run; the Product section is filled in at setup |
| `team/START.md` | The Head of Product's setup steps |
| `team/ORG-CHART.md` | How the Head of Product runs sub-agents, files, quality, release, succession |
| `team/WORKING-PREFERENCES.md` | How the user likes to work; every session follows it |
| `team/HANDOVER-TEMPLATE.md` | Used when a session retires |
| `team/QA-DEFINITION-OF-DONE-TEMPLATE.md` | The release bar, filled in per product |
| `assistant/CLAUDE.md` | The Personal Assistant's rules |
