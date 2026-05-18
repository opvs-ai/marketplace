# `@opvs-ai/skills-sdk` — the runtime-agnostic SDK

> Stub — TODO M-G.

## What this page will cover

The embeddable TypeScript SDK that wraps every marketplace skill in a single contract — `ToolSpec` + `executeTool` + `makeExecutor`. Used directly by:

- Any Node framework not on MCP (Vercel AI SDK, Mastra, Inngest Agent Kit, KaibanJS).
- Internal OPVS code that needs marketplace skills without going through the gateway.
- Codegen targets for runtimes like LangChain (JS) and LangGraph (JS).

### What you get

- One subpath export per skill family — `@opvs-ai/skills-sdk/agentboard`, `/agentdocs`, `/agentmemory`, `/opvs-protocol`, `/auth`, `/integrations`.
- Typed `ToolSpec[]` arrays per skill.
- `makeExecutor({ pat, baseUrl })` factory that returns a callable.
- Per-call response: the on-demand contract shape — `result`, `_guidance`, optional `_findings`, `telemetry_signal`.

### Auth

Same `OPVS_PAT` story as MCP. The SDK reads from `process.env.OPVS_PAT` by default, or take an explicit `{ pat: ... }` config.

### When to use SDK vs MCP

- **MCP** — your runtime speaks MCP natively. Zero glue code.
- **SDK** — your runtime speaks tool decorators, function calling, or some other DSL. Use the SDK as the executor inside whatever wrapper your runtime expects.

## Cross-links

- The MCP package family: [opvs-ai-mcp.md](opvs-ai-mcp.md)
- The codegen runtimes that wrap this SDK: [03-integration-patterns/code-generation-runtimes.md](../03-integration-patterns/code-generation-runtimes.md)
