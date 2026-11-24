# Start here

This repo sets up a design team in Claude Code that can run **many projects at once**:

```
You
 └─ Chief of Design              ← one hub session above every project
     ├─ <Project> - Manager      ← one per project; runs short-lived sub-agents for the hands-on work
     └─ Personal Assistant       ← holds your tools (Jira, calendar, docs, mail)
```

You talk to each project's Manager about that project, and to the Chief of Design about anything that applies to
every project: new projects, global rules, the template.

## What you need
- The **Claude desktop app** (Code tab). The team uses its session tools: starting sessions, sidebar groups, pins,
  messages between sessions.
- A folder for the hub, for example `~/Documents/Chief-of-Design/`. Projects get their own folders next to it.

## Set it up (about 10 minutes)
1. **Put this repo in the hub folder** (use the template, clone it, or download the ZIP).
2. **Install the skills** so every session can use them:

   ```bash
   cp -R skills/* ~/.claude/skills/
   ```

3. **Open the hub folder** in the Claude desktop app, Code tab, and start a new session on **Opus**.
4. Type: **"You are the Chief of Design. Set up the hub from START-HERE.md."** It will:
   - rename itself "Chief of Design", pin itself and create the sidebar groups "Executives" and
     "Connectors - Advisors";
   - start the **Personal Assistant** (Sonnet, low effort) in `assistant/`, pin it and record both ids in
     `PROJECTS.md`;
   - ask you a few questions, one at a time (your name, where projects should live, which tools you use) and write
     the answers into "The user's setup" in `CLAUDE.md`.
5. **Start your first project:** say **"New project"** to the Chief of Design. It asks for the name, creates the
   folder from `project-template/`, and starts that project's Manager, which asks you the project's setup questions.

## Day to day
- **Project work:** talk to "<Project> - Manager". Ask for anything: "audit the homepage", "give me 3 directions",
  "push". Its task list shows which jobs are running.
- **Across projects:** talk to the Chief of Design: "new project", "from now on, every project should…", "what's the
  status of everything?".
- **Tools:** ask the Personal Assistant to find a doc, check your calendar or update a ticket. It sends or changes
  nothing without your yes in its own chat.
- **Long chats:** when a Manager's chat gets long (300K tokens), it writes a handover and the Chief of Design starts
  the next version on your "ok". The old one stays as an Advisor you can ask about history.

## What doesn't come with a copy (by nature)
- **Chat history and memory:** every session starts fresh; the files are the team's memory.
- **Sidebar groups and pins:** the Chief of Design creates them during setup.
- **Tool sign-ins:** connect your tools in the app's connector settings. Nobody types passwords or tokens for you.
- **Session ids:** filled in as each session is created.

## Files
| Path | What it is |
|---|---|
| `CLAUDE.md` | The Chief of Design's rules: structure, jobs, successions, new projects |
| `PROJECTS.md` | The register of every project and its Manager |
| `project-template/` | Copied into every new project: its `CLAUDE.md` and `team/` (org chart, start steps, handover and QA templates, working preferences) |
| `assistant/CLAUDE.md` | The Personal Assistant's rules |
| `skills/` | Team skills: `project-kickoff`, `site-audit`, `page-redesign`, `design-review` |
| `handover/`, `notes/` | The Chief of Design's handovers and cross-project notes |
