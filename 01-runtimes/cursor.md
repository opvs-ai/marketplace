# Cursor

> Stub — TODO M-E. MCP-thin runtime — points at `@opvs-ai/mcp`.

Cursor is an MCP-capable IDE. Install is one `mcp.json` entry under Settings → Tools & MCP plus a brand-scoped credential.

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

For brands hitting the ~100-tool cap, use a scoped MCP — see [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md).

### 2. Authenticate

Same flow as Claude Code. `OPVS_PAT` is brand-scoped.

### 3. Call a tool

Marketplace skills appear as native tools after restart.

### 4. Maintenance

`npx -y @opvs-ai/mcp` picks up the latest. Revocation flows through the gateway grant-cache.

### 5. Sample code

A working `mcp.json` and a demo prompt lives in the content fill-in PR.

## Cross-links

- [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md)
- [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md)
