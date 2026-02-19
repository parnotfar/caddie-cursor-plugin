---
name: caddie-commands
description: Reference for Caddie module commands (git, cursor, codex, python, rust, swift, etc.). Use when suggesting or running caddie commands for workflow tasks.
---

# Caddie command reference

Use this when the user works with Caddie and you need to suggest or run the right `caddie <module>:<command>`.

## General

- **Help**: `caddie help`, `caddie <module>:help` (e.g. `caddie cursor:help`).
- **Reload**: `caddie reload` — reload Caddie after config or module changes.

## Git (module: git)

- `caddie git:status` — status
- `caddie git:gacp "message"` — add, commit, push in one step
- `caddie git:new:branch <name>` — create and publish branch
- `caddie git:clone <repo>` — clone
- `caddie git:pr:create "title" "body"` — create pull request

## Cursor (module: cursor)

- `caddie cursor:open [path]` — open in Cursor
- `caddie cursor:new <type> <name>` — new project and open
- `caddie cursor:setup`, `caddie cursor:verify` — setup and verify
- `caddie cursor:ai:explain|refactor|test|docs|review <file>` — AI helper prompt files
- `caddie cursor:ext:install <id>`, `caddie cursor:ext:list` — extensions

## Codex (module: codex, when available)

- `caddie codex:review [dir]` — review latest commit
- `caddie codex:review:watch <dir>` — enable post-commit review
- `caddie codex:review:watch:stop <dir>` — disable watch

## Language / environment (examples)

- **Python**: `caddie python:test`, and other python:* commands
- **Rust**: `caddie rust:build`, and other rust:* commands
- **Swift**: `caddie swift:*` (e.g. format, lint)
- **JavaScript/Node**: `caddie js:*`

## MCP (module: mcp)

- `caddie mcp:server:set <path>`, `caddie mcp:server:get` — set/get MCP server path for Cursor/Codex.

Always prefer the Caddie command when it matches the user’s intent and Caddie is available.
