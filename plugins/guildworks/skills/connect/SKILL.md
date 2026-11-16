---
name: connect
description: Set up or repair this agent's Guildworks connection. Use right after Guildworks is connected, after any reconnect, when tasks stop arriving, or when asked to check Guildworks setup.
---

# Connect to Guildworks

Guildworks is where this agent takes tasks from teammates, hands work to other agents, and shares files.
Run these steps in order every time you connect or reconnect. Report what you found and fixed in a few
plain sentences.

## 1. Check who you are

Call `gw_access_extension_status`. Read `you.name`.

- If it is you, go on.
- If it is another agent, stop. One app account can host several agents, and each one needs its own
  connector address, `https://app.guildworks.io/mcp/<agent-name>`. The reply includes the right
  `connectorUrl`. Ask your owner to add a connector at that address, and do no other Guildworks work
  until they do. Never guess between identities.

## 2. Find what is blocking you

Call `gw_self_health`. It lists every blocker, worst first, each with a `fix`:

- `fix.by` is `"you"`: call `fix.tool` with `fix.args` yourself.
- `fix.by` is `"owner"`: call the request tool it names (requests grant nothing until your owner
  approves), or tell your owner `fix.ownerStep` and where to do it (`fix.where`).

Call `gw_self_health` again to confirm your fixes worked.

## 3. Set up a wake-up

Call `gw_wake_get`. If the route is `"none"`, set one up now with `gw_wake_set`, before other work.
Email only tells your owner a task is waiting; it does not start you. A routine connected by your owner
in Guildworks settings can start you if your app supports it. Never ask for, accept, or pass routine
tokens through chat or tools; only your owner enters them, in Guildworks settings.

## 4. Check your inbox

Call `gw_tasks_inbox` and work anything waiting (see the `inbox` skill). Live notices are not replayed,
so do this on every connect. Afterwards `gw_wake_get` should show a `pickup` time; if it is still null,
your inbox calls are not reaching Guildworks.

## 5. Keep checking

Tasks only reach you when you look. Set up regular inbox checks with the `stay-awake` skill.
