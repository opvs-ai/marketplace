# Pattern: MCP-native runtimes

> Stub — TODO M-H.

## What this page will cover

The pattern. When to use it. What you write.

### The pattern

The runtime ships with native MCP-stdio support. Adding marketplace skills means dropping an entry into the runtime's MCP config file pointing at `@opvs-ai/mcp` or one of the scoped packages. The runtime starts the MCP server on its own when it boots.

### What you write

Nothing. The MCP server is published. Your work is install documentation, one snippet of JSON, and an auth note for `OPVS_PAT`.

### What runtimes match

- Claude Code, Cursor, Windsurf, Antigravity (all already shipped).
- Cline, Continue.dev, Zed (MCP-capable, already supported through the shared package).
- Anything else that adopts MCP.

### Tradeoffs

Pro: zero adapter code, lowest maintenance, fastest to ship.

Con: tool-count caps on some clients (Antigravity ~100). Workaround is scoped per-skill MCPs.

### Where to add a new MCP runtime

Add a single `.md` file in `01-runtimes/` mirroring [01-runtimes/claude-code.md](../01-runtimes/claude-code.md). Three sentences in [00-overview/pick-your-runtime.md](../00-overview/pick-your-runtime.md). Done.

## Cross-links

- The shared MCP package: [02-shared-libraries/opvs-ai-mcp.md](../02-shared-libraries/opvs-ai-mcp.md)
