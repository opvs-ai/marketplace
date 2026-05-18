# 01-runtimes

One section per agent runtime. Pick yours.

## Three runtime families

The marketplace plugs into runtimes through one of four [integration patterns](../03-integration-patterns/). Two of those patterns dominate:

**MCP-native** — the runtime speaks the Model Context Protocol over stdio. You add an `mcp.json` entry pointing at `@opvs-ai/mcp` and you are done. No glue code. Examples: Claude Code, Cursor, Windsurf, Antigravity.

**Plugin-based (OpenClaw family)** — the runtime loads native TypeScript or Python plugins. The marketplace ships a bundle that registers tools directly. Examples: OpenClaw, Hermes, Picoclaw.

**Codegen / decorator-based** — the runtime expects you to declare tools in its own DSL (LangChain `@tool`, CrewAI tool decorator, etc.). The marketplace SDK emits per-runtime wrappers from the same `schema.yaml`. Examples: LangChain, LangGraph, CrewAI, AutoGen, LlamaIndex.

## Runtimes covered today

### OpenClaw family

OpenClaw is OPVS' own gateway. Hermes and Picoclaw share the same plugin convention with minor tweaks.

- [openclaw/](openclaw/) — Native first-party. The reference plugin. (TODO M-C)
- [hermes/](hermes/) — `github.com/NousResearch/hermes-agent`. (TODO M-D)
- [picoclaw/](picoclaw/) — Lightweight OpenClaw variant. (TODO M-D)

### MCP-native

All four runtimes consume the same `@opvs-ai/mcp` package. The install guide is mostly a snippet of `mcp.json` plus the auth step.

- [claude-code.md](claude-code.md) — Anthropic CLI. (TODO M-E)
- [cursor.md](cursor.md) — Cursor IDE. (TODO M-E)
- [windsurf.md](windsurf.md) — Windsurf IDE. (TODO M-E)
- [antigravity.md](antigravity.md) — Google IDE. (TODO M-E)
- [gemini/](gemini/) — Gemini-based agents. Supports MCP and native function calling. (TODO M-E)

### Codegen runtimes

The marketplace emits per-runtime tool wrappers from the same skill schema.

- [langchain/](langchain/) — LangChain (Python and JS). (TODO M-F)
- [langgraph/](langgraph/) — LangGraph (Python and JS). (TODO M-F)

## More runtimes coming

About forty agent frameworks are on the roadmap — CrewAI, AutoGen, LlamaIndex, Pydantic AI, Mastra, Vercel AI SDK, Hermes, OpenDevin, MetaGPT, smolagents, Letta, and more. Each new runtime gets its own subdirectory here.

When a new runtime ships, [00-overview/pick-your-runtime.md](../00-overview/pick-your-runtime.md) gets a new row.

## What every runtime section contains

Whether single file or subdir, every runtime page answers the same five questions in the same order:

1. **Install.** What command or config change does the developer make?
2. **Authenticate.** How does the runtime get a brand-scoped credential to the marketplace?
3. **Call a tool.** What does a marketplace tool call look like from the agent's side?
4. **Maintenance.** How do version bumps and revocations propagate?
5. **Sample code.** A small end-to-end working example.
