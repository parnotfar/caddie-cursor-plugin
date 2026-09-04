# Release Notes

## 0.3.0 — 2026-09-04

- Updated Cursor guidance for caddie.sh 11.5's generated command and namespace help.
- Preserved the core-plus-supplemental skill model: core owns discovery and execution, while module skills add domain guidance.
- Added symmetric `--help` and `:help` examples without introducing a static command catalog.

## 0.2.0 — 2026-08-27

- Replaced stale static command catalogs with installed-CLI discovery
- Standardized agent-shell execution on `caddie agent:exec`
- Clarified that optional module skills compose with core Caddie and that optional plugins are not core modules
- Synchronized marketplace and plugin manifest versions

## 0.1.0

- Initial Cursor Marketplace plugin
