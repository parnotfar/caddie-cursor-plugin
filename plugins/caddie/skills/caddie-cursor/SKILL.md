---
name: caddie-cursor
description: Use Caddie's installed Cursor module for Cursor-specific workflows, discovering current commands before execution.
---

# Caddie + Cursor

## When to use

- User wants to open a project or folder in Cursor.
- User wants to set up or verify Cursor integration with Caddie.
- User wants AI-assisted explain/refactor/test/docs/review via Caddie’s prompt-file workflow.

## Discover current commands

```bash
caddie agent:exec core:module:commands cursor
caddie agent:exec cursor:help
caddie agent:exec cursor:<command> --help
caddie agent:exec cursor:<command>:help
```

Use only commands returned by the installed module. Execute agent-shell commands through `caddie agent:exec`.

## Notes

- Requires both Caddie and Cursor. Use discovered diagnostic commands rather than assuming a specific command name.
- This thin Cursor skill composes with the core Caddie discovery skill and does not duplicate the live command catalog. Caddie 11.5 or later supplies symmetric command and namespace help from live metadata.
