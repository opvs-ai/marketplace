# Antigravity

> Stub — TODO M-E. MCP-thin runtime — points at scoped `@opvs-ai/mcp-*` packages.

Antigravity is Google's MCP-capable IDE. Same shape as Cursor and Windsurf, but with a hard ~100-tool cap that pushes most brands toward scoped per-skill MCPs instead of the all-in-one `@opvs-ai/mcp`.

## What this page will cover

### 1. Install

For a single skill area (recommended for most brands):

```json
{
  "mcpServers": {
    "opvs-agentboard": {
      "command": "npx",
      "args": ["-y", "@opvs-ai/mcp-agentboard"],
      "env": { "OPVS_PAT": "opvs_pat_..." }
    },
    "opvs-agentdocs": {
      "command": "npx",
      "args": ["-y", "@opvs-ai/mcp-agentdocs"],
      "env": { "OPVS_PAT": "opvs_pat_..." }
    }
  }
}
```

Picking the right scoped packages: see [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md).

### 2. Authenticate

Same flow as Claude Code. `OPVS_PAT` is brand-scoped.

### 3. Call a tool

Each scoped MCP exposes its own tool namespace, all natively callable.

### 4. Maintenance

`npx -y` keeps each scoped package current.

### 5. Sample code

A working `mcp.json` with three scoped MCPs and a demo prompt lives in the content fill-in PR.

## Cross-links

- [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md)
- [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md)
- Historical context on the tool-cap discovery: legacy memory `antigravity-debrief-2026-04-26.md`.
