---
name: caddie-commands
description: Use the installed Caddie CLI as the source of truth for module discovery and command execution in Cursor agent shells.
---

# Caddie command discovery

This Cursor marketplace skill follows the core Caddie protocol. It intentionally does not carry a static command catalog because core and optional plugin modules are released independently.

## Discover before acting

```bash
caddie agent:exec core:modules:list
caddie agent:exec core:module:commands <module>
caddie agent:exec <module>:help
caddie agent:exec <module>:<command> --help
caddie agent:exec <module>:<command>:help
```

Treat discovery output as authoritative. Never infer a command from this skill, old documentation, or another Caddie installation.

On caddie.sh 11.5.0 or later, the last two forms are symmetric and also work for namespaces. A module may override generated output with richer help, but its supplemental skill still owns only domain guidance and safety.

## Execute in agent shells

Use `caddie agent:exec` so Caddie loads a fresh environment without inherited Bash function state:

```bash
caddie agent:exec <module>:<command> [args]
```

Prefer a discovered Caddie wrapper when it matches the requested outcome. If no wrapper exists, use the underlying tool and state the fallback.

## Module skills

Core Caddie owns the discovery and execution protocol. An optional module may provide a separate thin skill for domain safety, sequencing, or interpretation. Apply both when such a skill is installed; do not expect the module skill to duplicate its command list.

Optional modules, including Git workflow commands, must be discovered rather than assumed to be part of core.

## Reload after installation

After installing or upgrading core or a plugin, run `caddie reload`, then repeat discovery.
