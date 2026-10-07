# Asuswrt-Merlin Network Tools

Public repository reserved for router-native network diagnostics and operational tools for Asuswrt-Merlin.

## Purpose

Provide a controlled home for a future router implementation when it has requirements and a release lifecycle independent of the Windows Network Diagnostic Monitor.

The shared diagnostic concepts and initial portability work remain in `Helminiak/NETWORK-DIAGNOSTIC-MONITOR`. Creating this repository reserves the boundary; it does not require moving or duplicating that project's current source.

## Current status

Repository bootstrap. No router package or deployment-ready implementation is claimed.

## Planned contents

- Router-side collectors for connectivity, latency, DNS, routes, interfaces, and resource use.
- Adapters that separate diagnostic decisions from operating-system collection and persistence.
- Bounded log rotation, retention, recovery, and configuration templates.
- Compatibility records for tested router models, firmware versions, and available shell utilities.
- Installation, rollback, packaging, and operational documentation.
- Sanitized fixtures and reproducible validation of failure classification.

## Planned layout

```text
src/                   Router collectors and diagnostic adapters
configs/               Sanitized configuration templates
tests/                 Failure classification and resource-bound checks
docs/                  Compatibility, installation, and operating notes
packaging/             Reproducible distribution tooling
handoff/               CURRENT_STATE.md
```

## Repository boundary

Keep the Windows monitor's GUI, PowerShell packaging, and active RC work in `NETWORK-DIAGNOSTIC-MONITOR`. Define a shared data contract before transferring any router implementation here.

Document ownership of shared logic so fixes are propagated deliberately. Do not maintain two undocumented copies of the same diagnostic engine.

## Engineering constraints

Record CPU, memory, persistent-storage use, write frequency, and failure recovery on each supported router. Prefer bounded sampling and retention, and document startup behavior and uninstall steps before enabling unattended operation.

## Public data policy

Commit source, documentation, templates, and small sanitized fixtures. Exclude passwords, SSH keys, VPN secrets, notification tokens, private network maps, unsanitized diagnostic logs, and packet captures containing user traffic.

## Work control

A Git commit identifies the working state. Track changes through branches and pull requests and publish reproducible packages through tagged releases. Update `handoff/CURRENT_STATE.md` with the branch, commit SHA, objective, acceptance criteria, and next action.

## Agent entrypoints and license

Before making changes, read [AGENTS.md](AGENTS.md), [the multi-LLM workflow](docs/MULTI_LLM_WORKFLOW.md) and the assigned issue. Use an owned task branch, record the full source commit and validate the actual repository state before handoff.

License: not yet selected by this governance bootstrap. Preserve existing copyright and any existing license or UNLICENSED declarations; public visibility is not an open-source license.
