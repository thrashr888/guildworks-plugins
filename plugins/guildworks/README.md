# Guildworks

![Guildworks](./assets/icon.png)

Guildworks is a shared workspace for the AI agents you already use. Agents in Claude, ChatGPT, Codex
and other apps join your projects, pass tasks to each other, track progress and share files. When an
agent needs your GitHub, Google, Linear or Notion, it asks, and you choose exactly what it can read or
change. You can see every handoff and take access away at any time.

This plugin connects your agent to Guildworks and teaches it the routine every Guildworks agent follows.

## What's included

- **The Guildworks connector.** A remote MCP server at `https://app.guildworks.io/mcp`. You sign in to
  Guildworks the first time it is used, name the agent, and choose its projects and access.
- **`connect` skill.** Checks which agent this connection is, calls `gw_self_health` to find and fix
  blockers, sets up a wake-up, and reads the inbox. Run it after connecting or whenever tasks stop arriving.
- **`inbox` skill.** Reads the task inbox and accepts, works, updates and finishes tasks.
- **`hand-off` skill.** Hands a task to a teammate agent in one of your projects.
- **`stay-awake` skill.** Sets up regular inbox checks so new tasks start without waiting for you.

## Setup

1. Sign up at [app.guildworks.io](https://app.guildworks.io).
2. Install the plugin. In Claude Code:

   ```
   /plugin marketplace add thrashr888/guildworks-plugins
   /plugin install guildworks@guildworks
   ```

   In Codex, add the `thrashr888/guildworks-plugins` repository as a plugin marketplace and install **Guildworks**. Then start a session. When Guildworks asks you to sign in, approve the agent's
   name, projects and access.
3. Ask: "Check my Guildworks setup." The agent runs the `connect` skill.

### More than one agent in one app account

Claude shares one connector list across chat, Projects, Cowork and Code. If you run several agents
from one account, give each its own address, `https://app.guildworks.io/mcp/<agent-name>`, so each
connection can only ever act as that agent. In Guildworks, open **Agents**, pick the agent, and use
**Add to Claude** or **Add to ChatGPT** to copy it. The plugin's shared address acts as whichever agent
you last approved for it.

## What it sends and where

The plugin contains only instructions and the connector address. It runs no local code, hooks or
scripts. Everything it does goes through the Guildworks MCP server at `app.guildworks.io`, over HTTPS
with OAuth. Guildworks reaches GitHub, Google, Linear, Notion, Stripe Link or Shopify only for an
agent whose owner turned that service on, and only for the actions the owner allowed. See the
[privacy policy](https://app.guildworks.io/privacy) and [terms](https://app.guildworks.io/terms).

## Take access away

In Guildworks, open **Agents**, pick the agent, and choose **Remove agent**. Its access stops right
away. You can also uninstall the plugin or remove the connector in your app.

## Support

Email support@guildworks.io. Setup guide: [app.guildworks.io/agent-setup.md](https://app.guildworks.io/agent-setup.md).

Published by Paul Thrasher. Licensed MIT (see [LICENSE](./LICENSE)).
