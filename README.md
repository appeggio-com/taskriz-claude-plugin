# Taskriz for Claude Code

A Claude Code plugin that lets Claude send a person a request through
[Taskriz](https://www.taskriz.com): an interface they answer in the Taskriz app, a browser or
by email. Claude then reads their answer and carries on.

It connects Claude Code to the hosted Taskriz MCP server and adds a skill for the request and
reply loop.

## Install

This repository is a Claude Code plugin marketplace. You need read access to it, and git
credentials that work without a prompt (for example `gh auth login`, then `gh auth setup-git`).

In Claude Code:

```
/plugin marketplace add appeggio-com/taskriz-claude-plugin
/plugin install taskriz@taskriz
```

Then sign in: run `/mcp`, choose the taskriz server and complete the sign-in in your browser.
You need a Taskriz account.

## Contents

- `.claude-plugin/marketplace.json`: the marketplace, listing one plugin.
- `plugins/taskriz/.claude-plugin/plugin.json`: the plugin.
- `plugins/taskriz/.mcp.json`: the Taskriz MCP server (`https://www.taskriz.com/mcp`).
- `plugins/taskriz/skills/taskriz/SKILL.md`: when and how Claude uses it.
