# ux-cc-workflow

A ready-to-use team setup for running UX and design work with **Claude Code** (desktop app, Code tab), across one
project or many.

```
You
 └─ Chief of Design              ← one hub session above every project
     ├─ <Project> - Manager      ← one per project; runs short-lived sub-agents for the hands-on work
     └─ Personal Assistant       ← holds your tools (Jira, calendar, docs, mail)
```

- **Chief of Design:** manages the Managers. Starts new projects, rolls out rules that apply everywhere, and starts a
  fresh Manager when one's chat gets long. Does no project work itself.
- **One Manager per project:** plays PM, design manager and lead. It splits each job into small pieces and runs
  sub-agents for them, in waves, each on the model the job needs: Opus for design calls and reviews, Sonnet for
  build-out and fixes, Haiku for lookups (or any other model your rules name).
- **Personal Assistant:** one shared session for your tools. It fetches for anyone, but sends or changes nothing
  without your yes.

Everything the team knows lives in plain files, so work survives long chats and handovers. It holds no project
content: each Manager asks you about its project and fills it in.

## Quick start

1. Click **Use this template** (or download the ZIP) and put the files in a hub folder, for example
   `~/Documents/Chief-of-Design/`.
2. Install the skills:

   ```bash
   cp -R skills/* ~/.claude/skills/
   ```

3. Open the hub folder in the Claude desktop app, Code tab, and start a new session on Opus.
4. Type: **"You are the Chief of Design. Set up the hub from START-HERE.md."**
5. Then say **"New project"** whenever you start one.

Full details are in [START-HERE.md](START-HERE.md).

## What's inside

| Path | What it is |
|---|---|
| `CLAUDE.md` | The Chief of Design's rules: structure, jobs, successions, new projects |
| `PROJECTS.md` | The register of every project and its Manager |
| `project-template/` | Copied into every new project: org chart, start steps, working preferences, handover and QA templates |
| `assistant/CLAUDE.md` | The Personal Assistant's rules |
| `skills/` | Four team skills: `project-kickoff`, `site-audit`, `page-redesign`, `design-review` |

## How it works

- **Work in files, not chat.** Each job gets its own folder in the project's `team/work/` with a brief and a report.
- **Quality before release.** Nothing ships until a QA pass checks it at desktop, tablet and phone widths.
- **Succession.** Managers retire at about 300K tokens: they write a handover, the Chief of Design starts the next
  version on your "ok", and the old one stays as an "Advisor" you can ask about history.
- **You stay in charge.** Anything outward-facing (pushes, deploys, messages to people) waits for your yes.

## Requirements

- The Claude desktop app with the Code tab (the team uses its session tools: starting sessions, sidebar groups,
  pins, messages between sessions).
- Optional: connectors for Jira, Google Calendar, Docs, Drive or Gmail, for the Personal Assistant.

## Licence

MIT. See [LICENSE](LICENSE).
