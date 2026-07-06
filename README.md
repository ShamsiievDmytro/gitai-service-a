<!-- VENTION-SDLC-MANAGED:BEGIN v=0.0.1 -->
## Vention SDLC workspace — managed by `vsdlc`

This README block is managed by the Vention SDLC framework (`@vention/sdlc` v0.0.1).
The bytes between the BEGIN / END markers are rewritten on every `vsdlc install` run.

- **Workspace:** `gitai-service-a` (scenario: `single-repo`)
- **Issue tracker:** `youtrack` at `https://yt-wod.ventionteams.com/` (project: `WOD`)

## Getting started

New developers landing in this workspace should run the following steps in order:

- Clone the workspace repository with `git clone` and `cd` into the resulting directory.
- Install the per-developer environment by running `vsdlc install` from the workspace
  root. The framework will scaffold the IDE wiring, hook configurations, and shell-rc
  managed blocks for your machine.
- Install the toolchain by running `mise install` after `vsdlc install` completes. The
  per-tool versions are pinned by the framework so every workspace member runs the same
  binaries.

Refer to your team's onboarding notes OUTSIDE the BEGIN / END markers for any
team-specific steps not covered above. See `AGENTS.md` for the full agent guide
(work types, MCP usage, slash-command catalogue, hook behaviour).

## Issue tracker integration

The framework wires this workspace to the configured issue tracker via the
`issue-tracker` capability adapter.

- **Adapter:** `youtrack`
- **Base URL:** `https://yt-wod.ventionteams.com/`
- **Project key:** `WOD`
- **Token environment variable:** $YT_TOKEN or $YOUTRACK_TOKEN or $VSDLC_YOUTRACK_TOKEN (the framework resolves the token from
  the first non-empty match in declaration order; never hard-code it).

Agents that need to read or write issue-tracker state MUST go through the adapter
operations — never call the vendor CLI or vendor MCP tool directly.

## WoD-Atlas integration

The framework uses the WoD-Atlas platform for metric-event submission on unit-of-work
completion — see the Hook behaviour summary in `AGENTS.md` for details. The in-scope MCP
tool family is `mcp__WoD-Atlas__*` (chiefly `track_metric_event`); the MCP server
registry key in `.mcp.json` is `WoD-Atlas`.


This workspace is bound to a WoD-Atlas workspace id; agents must pass
`X-Workspace-Id: my-forge-id` on every Forge MCP call so the event is bound to the
right tenant.

## What this block is

Everything between the BEGIN / END markers is framework-managed and gets rewritten on
every `vsdlc install`. Add your team's onboarding notes OUTSIDE the markers — they will
be preserved byte-for-byte across upgrades.

> Run `vsdlc install` to refresh this block. Do not edit between the markers.
<!-- VENTION-SDLC-MANAGED:END -->

# Service A
Example sibling service repository for git-ai multi-repo testing.
