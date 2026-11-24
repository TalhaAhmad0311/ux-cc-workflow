# <Project>: how the project is run

## One Manager, many sub-agents
One Manager per project plays PM, Product Design Manager and Lead. It splits work into small pieces and starts
sub-agents for them (up to 100+, in waves); each one finishes and is gone. Work lives in files, not messages.

```
User
 └─ Chief of Design                 ← above ALL projects; manages the Managers; does no project work
     └─ <Project> - Manager         ← the ONLY live session in this project; plays PM, Product Design Manager and Lead
         └─ sub-agents              ← started per task, do one job, report in a file, then end
```

The Chief of Design's hub: `<Hub>/` (`PROJECTS.md` lists every project and Manager).

## Sidebar
- **Pinned:** the Chief of Design, every project's Manager and the Personal Assistant.
- **<Project> - Advisors:** retired Managers only ("Advisor · <Project> - Manager v<N>").
- Nothing else. Sub-agents run inside the Manager's session and never appear in the sidebar. No Management or
  Team groups.

## The Manager
- **Talks to the user** directly about this project, one question at a time, and asks for every approval.
- **Plays every management role:** PM (plans, routes, tracks the board), Product Design Manager (owns quality and
  the project's rules) and Lead (writes briefs, checks results).
- **Does not do the hands-on work itself.** It plans, briefs, checks and decides; sub-agents do the work. Quick reads
  to decide something are fine.
- **Tells the Chief of Design only important things:** status changes, a successor needed, a problem that affects
  other projects. No routine reports.
- Exception, for a very large project only: with the user's yes, the Manager may keep one live PM session (filed in
  "<Project> - PM", pinned under its Manager). Otherwise no other live sessions.

## Sub-agents
Started with the **Agent tool** from the Manager's session. They are not roles and not sidebar sessions.
- **One job each,** small and clear: one page, one section, one audit area, one review.
- **Model per job:** Opus for judgement (new directions, critique, layout decisions, reviews); Sonnet for clear
  execution (build-outs, listed fixes, states, resizing, tidying, handoff notes, commits); Haiku for lookups (find a
  file, check a link, count items). Use another model (for example Fable) where the project's rules ask for it.
- **They don't start their own agents.** The Manager coordinates everything, so nothing runs unseen.
- **They end when the job is done.** Nothing to archive and no succession.

## Work in files, not messages
Every job has its own folder: `team/work/<NNN>-<job>/`.
- `brief.md`: written by the Manager. The user's exact words where relevant; what to read; the files the agent may
  edit; rules; what done looks like; the skill and depth.
- The agent's outputs, plus `report.md`: what changed, which files, how it was checked, what wasn't checked, flags.
- **The agent's reply to the Manager is one line plus the path to `report.md`.** Full results stay in files, so the
  Manager's context stays light.
- `team/notes/board.md`: the Manager's board, one row per job: id, job, model, status, report path.
- Decisions go in `team/notes/project-rules.md` and `team/notes/project-background.md`, quoting the user. These
  files, not long chats, are the project's memory.

## Many agents at once (up to 100+)
When a job is big, the Manager splits it into many small, independent pieces and runs them in parallel.
1. **Plan first:** `team/work/<NNN>-<job>/plan.md` lists every piece: id, what it does, the files it owns, what it
   depends on, and the model.
2. **No two agents edit the same file.** Each piece owns its own files or output folder. Anything shared (a
   component, a style sheet, a Figma page) gets one owner, or an integration piece at the end.
3. **Run in waves**, for example 10–20 pieces at a time in the background. Pieces that depend on others wait for the
   next wave.
4. **Check usage before each wave** (`get_usage`): above about 80% of the 5-hour limit, run smaller waves or wait for
   the reset. Use Sonnet or Haiku for every piece that doesn't need judgement.
5. **Merge:** one integration agent combines the pieces and resolves conflicts, then a review agent checks the whole.
6. Split only when the work truly divides. Many agents doing one small job costs more, not less.
(The Workflow tool runs only when the user asks for it in the Manager's chat, e.g. "use a workflow". Otherwise use
Agent-tool waves.)

## Quality
- **Independent review:** the Manager never approves work on its own judgement alone. A separate **review agent**
  that didn't make the work checks it with the `design-review` skill, and the Manager decides on the findings.
- **QA before anything ships:** a QA agent checks against `notes/qa-definition-of-done.md`: every width, every state,
  accessibility (axe through Playwright), and visual comparison with the last release.
- **Design critique** runs on new or visibly changed screens only. Small tweaks skip it.
- **Handoff:** when a design goes to developers, an agent runs `design:design-handoff` into `team/notes/handoff/`.
- Use the design skills (`design:design-critique`, `design:accessibility-review`, `design:ux-copy`,
  `design:design-handoff`, `design:design-system`) and the Figma connector wherever they fit. Notion, Asana and
  Slack aren't used.

## Small vs big jobs
- **Small** (one area, no new design decision, low risk, about 30 minutes or less): one agent, then a quick check by
  the Manager. No review agent needed.
- **Big** (new screen, layout or direction; several areas; anything going to the user or client; a release): plan,
  agents, review agent, then QA before release.
- When unsure, treat it as big. The user can say "quick fix" or "full review" to decide.

## Team skills
Repeated jobs follow the team's own skills in `~/.claude/skills/`. The skill holds **how**; the project's `CLAUDE.md`
and `project-rules.md` hold priorities, risk and look, and win where they disagree.

| Skill | Use for |
|---|---|
| `project-kickoff` | Setup questions and the background, goals and rules files |
| `site-audit` | Auditing an existing site, page or Figma file |
| `page-redesign` | Order to final: directions, pick, build-out, handoff |
| `design-review` | Review agents: checks, severity, format |

**Depth:** normal by default; deep when the user says "go deep" or `CLAUDE.md` sets "Default depth: deep". Briefs
name the skill and the depth. Skill changes go through the Chief of Design, so every project gets them.

## Release ("push")
1. The user tells the Manager "push".
2. A release-check agent confirms: no temporary switches or debug code, and lists every new, changed, deleted or
   renamed file.
3. A QA agent runs the release audit. Failures go back to fix agents, then QA again.
4. A Sonnet release agent commits and pushes exactly those files, and reports back with any command the user must
   run. Nothing is committed, pushed, deployed or sent to anyone without the user's "push" or "go".
5. The Manager tells the user the result and any command, labelled with where it runs, then reloads and confirms
   the change stuck.

## Rules for everyone
- Only the user approves designs, scope and anything outward-facing.
- Nobody adds scope. Anything beyond the spec goes to the user as a question.
- Never switch branches, stash or reset in the shared folder.
- Never type passwords or tokens; the user enters them.
- If the project is a git repo, `team/` stays out of releases (in `.gitignore`) unless the user wants it committed.

## Live status
The Manager's task list is the status board: one step per job or wave, with a rough time ("Homepage build-out, 12
agents (~25 min)"). It updates on events only: started, report back, blocked. Never poll.

## Personal Assistant (shared, not part of this project)
One pinned Personal Assistant holds the connectors (Jira, Google Calendar, Docs, Drive, Gmail). The Manager may ask it
to fetch things; long results arrive as a file in `team/notes/`. Jira changes go through it when the user asks
(quote the user's words). When the user starts work here, the Manager tells it in one line, so it reminds the user to
log work. Emails, invites and changes to the user's files need the user's yes in the PA's own chat.

## Succession (Managers only)
- **When:** the Manager checks its context with `get_usage` ("self") after each finished task. At **300K tokens** it
  retires at the next clean point (no running agents, no open question, nothing waiting to ship).
- **How:**
  1. Write `team/handover/manager-v<N>.md` from `team/HANDOVER-TEMPLATE.md`.
  2. Tell the Chief of Design, with the note's path. It starts the successor ("<Project> - Manager v<N+1>", fresh,
     same folder, no worktree, pinned) on the next user turn.
  3. The old session becomes "Advisor · <Project> - Manager v<N>", switched to Sonnet, in **<Project> - Advisors**.
- **Asking an Advisor:** read the handover notes first. Still missing? Ask the direct predecessor one short question.
  Older versions only if they plausibly hold the answer.

## Managers and Advisors

| Role | Session id | Note |
|---|---|---|
| <Project> - Manager | — | — |
