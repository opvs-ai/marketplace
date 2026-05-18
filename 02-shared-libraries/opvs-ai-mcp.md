# `@opvs-ai/mcp` — the shared MCP server

> Stub — TODO M-G.

## What this page will cover

The MCP package family every MCP-capable runtime can use. One install path, two shapes.

### The two shapes

**All-in-one** — `@opvs-ai/mcp`. Every marketplace skill the installing brand has access to, in one stdio server. Use when the client has no tool-count cap (Claude Code, Cursor, Windsurf usually).

**Scoped per-skill** — `@opvs-ai/mcp-agentboard`, `@opvs-ai/mcp-agentdocs`, `@opvs-ai/mcp-agentmemory`, `@opvs-ai/mcp-opvs-protocol`, `@opvs-ai/mcp-auth`, `@opvs-ai/mcp-integrations`. Use when the client enforces ~100-tool caps (Antigravity, possibly Claude Desktop). One MCP server per skill family.

### Auth — `OPVS_PAT`

The PAT is brand-scoped. Provisioning flow:

1. `opvs auth request -w <workspace-slug> -e <admin-email>` from the OPVS CLI.
2. Admin clicks Approve in the email.
3. The PAT lands in `~/.opvs/config.json` and the runtime's MCP env block.

The PAT is the only credential the MCP server needs. Brand pinning, entitlement checks, and credential resolution all happen server-side at `/api/v1/skill_call`.

### What this package does NOT do

- It does not embed credentials for downstream services (SpiderIQ, Blotato, OpenAI, etc.). Those credentials are resolved per-brand inside OPVS at call time.
- It does not run on the runtime's host except as a thin stdio relay. The actual tool execution is server-side.

### Maintenance

`npx -y` always pulls the latest. Pin a version in `mcp.json` if you need reproducibility.

## Cross-links

- Per-runtime install entries:
  - [01-runtimes/claude-code.md](../01-runtimes/claude-code.md)
  - [01-runtimes/cursor.md](../01-runtimes/cursor.md)
  - [01-runtimes/windsurf.md](../01-runtimes/windsurf.md)
  - [01-runtimes/antigravity.md](../01-runtimes/antigravity.md)
- The on-demand contract every MCP tool returns: [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md)
