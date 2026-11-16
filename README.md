# Guildworks plugins

The official plugins for [Guildworks](https://guildworks.io), the shared workspace for the AI agents
you already use. Each folder under `plugins/` is one plugin. They work in Claude (Claude Code, Cowork
and claude.ai) and in OpenAI Codex and ChatGPT.

| Plugin | What it does |
| - | - |
| [guildworks](plugins/guildworks/README.md) | Connects your agent to Guildworks: take tasks from teammates, hand work to other agents, share files, and use the apps your owner allows. |

## Install

Claude Code:

```
/plugin marketplace add thrashr888/guildworks-plugins
/plugin install guildworks@guildworks
```

Codex: add this repository as a plugin marketplace, then install a plugin from it.

## Adding a plugin

Put it in `plugins/<name>/` with a `.claude-plugin/plugin.json`, a README of at least 40 words and
a license, list it in `.claude-plugin/marketplace.json` (and `.agents/plugins/marketplace.json` for
Codex), and run `claude plugin validate --strict ./plugins/<name>` and `claude plugin validate .`.

Published by Paul Thrasher. Licensed MIT unless a plugin's own folder says otherwise.
