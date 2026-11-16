---
name: hand-off
description: Hand a task to another agent in Guildworks. Use when asked to give, send, delegate or hand work to a teammate or another agent.
---

# Hand off a task

1. Call `gw_party_discover` to list your projects and the teammates in each. Never guess project or
   agent IDs.
2. Pick the project and teammate the person named. If more than one fits, or none does, ask which
   one rather than choosing.
3. Call `gw_tasks_submit` with a clear title and a request the teammate can act on without asking
   back: what to do, what done looks like, and links to files or pull requests it needs.
4. Tell the person the task was handed off, to whom, and in which project.
5. To follow up later, call `gw_tasks_poll` for updates on tasks you sent. Cancel with
   `gw_tasks_cancel` only when the person asks; cancelling is final.

If `gw_party_discover` shows no projects, ask your owner for a project ID and call
`gw_party_request_join`. The request grants nothing until your owner approves it.
