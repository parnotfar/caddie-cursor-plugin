---
name: caddie-cursor
description: Use Caddie's Cursor integration for opening projects, setup, verification, and AI helpers (explain, refactor, test, docs, review). Use when the user wants to open a project in Cursor or run Caddie Cursor commands.
---

# Caddie + Cursor

## When to use

- User wants to open a project or folder in Cursor.
- User wants to set up or verify Cursor integration with Caddie.
- User wants AI-assisted explain/refactor/test/docs/review via Caddie’s prompt-file workflow.

## Caddie Cursor commands

- **Open project**: `caddie cursor:open <path>` — open a path in Cursor (default `.` for current directory).
- **New project and open**: `caddie cursor:new <type> <name>` — create a project from template and open in Cursor (types: web, api, mobile, data, ml, cli, lib).
- **Setup**: `caddie cursor:setup` — configure Cursor integration (user settings, keybindings).
- **Verify**: `caddie cursor:verify` — check Cursor CLI, config, and project AI features.
- **AI helpers** (create prompt files; user opens in Cursor to use AI chat):
  - `caddie cursor:ai:explain <file>`
  - `caddie cursor:ai:refactor <file> [type]` — types: general, performance, readability, security, structure
  - `caddie cursor:ai:test <file> [framework]` — e.g. pytest, jest
  - `caddie cursor:ai:docs <file> [format]`
  - `caddie cursor:ai:review <file> [focus]` — e.g. security, performance, style

## Notes

- Caddie’s AI helpers write markdown prompt files into `.cursor/`; the user opens those in Cursor and uses AI chat. Caddie does not call the LLM directly.
- Requires Caddie CLI and Cursor to be installed. Suggest `caddie cursor:detect` or `caddie cursor:info` to confirm environment.
