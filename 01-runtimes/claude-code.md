# Claude Code

> Stub — TODO M-E. MCP-thin runtime — points at `@opvs-ai/mcp`.

Claude Code is Anthropic's terminal CLI agent. It speaks the Model Context Protocol natively. Install is one `.mcp.json` entry plus a brand-scoped credential.

## What this page will cover

### 1. Install

Add an entry like this to `~/.claude.json` or the workspace's `.mcp.json`:

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

For brands hitting the 100-tool client cap, swap `@opvs-ai/mcp` for a scoped per-skill package — see [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md).

### 2. Authenticate

`OPVS_PAT` is a brand-scoped personal access token. The full provisioning flow is in [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md) — `opvs auth request` from the OPVS CLI triggers an email approval, and after click-through the PAT is written to `~/.opvs/config.json`.

### 3. Call a tool

Once Claude Code is restarted, every marketplace skill installed for this brand appears as a native tool — `agentboard_createTask`, `agentdocs_searchPages`, etc. The agent calls them with no further configuration.

### 4. Maintenance

The MCP server runs `npx -y @opvs-ai/mcp`. New versions arrive on `npm install` or next `npx -y` fetch.

### 5. Sample code

A minimal `.mcp.json` and a one-prompt screencast lives in the content fill-in PR.

## Cross-links

- The shared MCP package: [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md)
- The on-demand contract Claude Code sees: [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md)
