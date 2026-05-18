# 02-shared-libraries

The three things every runtime adapter shares. Read whichever applies to your install path.

- [opvs-ai-mcp.md](opvs-ai-mcp.md) — The MCP server every MCP-capable runtime consumes. One all-in-one package plus six scoped per-skill packages for clients with a tool cap.
- [opvs-ai-skills-sdk.md](opvs-ai-skills-sdk.md) — The runtime-agnostic TypeScript SDK. Used directly by Node frameworks (Vercel AI SDK, Mastra) and indirectly by everything that wraps it.
- [per-runtime-knowledge-files.md](per-runtime-knowledge-files.md) — `opvs-skills emit-runtime` output. The Knowledge Items / system-prompt bundles that codegen and function-calling runtimes need.

All three pages are stubs (TODO M-G).
