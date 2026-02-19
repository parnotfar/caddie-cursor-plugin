# caddie-cursor-plugin

Cursor Marketplace plugin for [Caddie.sh](https://github.com/parnotfar/caddie.sh). Makes the Cursor agent **Caddie-aware**: it prefers `caddie <module>:<command>` when appropriate and follows Caddie codebase conventions when editing the Caddie repo.

## What is Caddie?

Caddie.sh is a modular Bash development environment manager (“common language for tooling”). You run commands like:

- `caddie git:gacp "message"` — add, commit, push
- `caddie cursor:open .` — open current folder in Cursor
- `caddie python:test`, `caddie rust:build` — language workflows
- `caddie codex:review` — code review on the latest commit

See the [Caddie.sh repo](https://github.com/parnotfar/caddie.sh) for install and full docs.

## What this plugin does

- **Rules**: Prefer Caddie commands over raw git/cursor/python/etc. when the user or project uses Caddie; when editing the Caddie codebase, follow AGENTS.md (modules, Makefile, CLI output, lint).
- **Skills**: Caddie + Cursor (open, setup, verify, AI helpers); Caddie command reference (git, cursor, codex, and other modules).

The plugin does **not** replace the Caddie CLI. You still need Caddie installed; this plugin teaches the Cursor agent when and how to use it.

## Install

1. **Install Caddie** (required): [Caddie.sh](https://github.com/parnotfar/caddie.sh) — clone, `make install`, source your shell profile.
2. **Install the plugin**: From the [Cursor Marketplace](https://cursor.com/marketplace) (when published), or install from this repo per Cursor’s “install from repo” flow.

## Validate

From the repo root you need Node.js to run the Cursor template validator. If you use Caddie and don’t have Node yet, set up a JavaScript environment first, then run the script:

```bash
caddie js:setup          # install Node.js and NVM (only if needed)
node scripts/validate-template.mjs
```

## Layout

- `.cursor-plugin/marketplace.json` — marketplace manifest (one plugin: `caddie`).
- `plugins/caddie/` — the Caddie plugin:
  - `.cursor-plugin/plugin.json` — name, description, logo, rules, skills.
  - `rules/` — prefer Caddie commands; Caddie codebase (AGENTS.md) conventions.
  - `skills/` — `caddie-cursor`, `caddie-commands`.
  - `assets/logo.svg` — plugin logo.

## Publish

When ready for the Cursor Marketplace: ensure `node scripts/validate-template.mjs` passes, then submit via [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish) or the Cursor team (e.g. Slack or kniparko@anysphere.com).

## License

Apache-2.0 (aligns with Caddie.sh).
