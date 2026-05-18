# Windsurf

> Stub — TODO M-E. MCP-thin runtime — points at `@opvs-ai/mcp`.

Windsurf is Codeium's MCP-capable IDE. Same install shape as Cursor and Claude Code — one `mcp.json` entry plus a brand-scoped credential.

## What this page will cover

### 1. Install

```json
{
  "mcpServers": {
    "opvs": {
      "command": "npx",
      "args": ["-y", "@opvs-ai/mcp"],
      "env": { "OPVS_PAT": "opvs_pat_..." }
    }
  }
}
```

The Windsurf-specific config file path lives at `~/.codeium/windsurf/mcp_config.json` — confirm in content fill-in.

For brands hitting the ~100-tool cap, use scoped MCPs — see [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md).

### 2. Authenticate

Same flow as Claude Code. `OPVS_PAT` is brand-scoped.

### 3. Call a tool

Marketplace skills appear as native tools after restart.

### 4. Maintenance

`npx -y @opvs-ai/mcp` keeps current.

### 5. Sample code

A working `mcp_config.json` and a demo prompt lives in the content fill-in PR.

## Cross-links

- [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md)
- [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md)
