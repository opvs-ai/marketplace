# Pick your runtime

> Stub — TODO M-B. Content fill-in lands in a follow-up PR.

## What this page will cover

A short table mapping your runtime to the right install section and the right integration pattern.

The shape will be:

| Runtime | Adapter type | Install guide |
|---|---|---|
| OpenClaw | Native plugin | [01-runtimes/openclaw/](../01-runtimes/openclaw/) |
| Hermes | Native plugin | [01-runtimes/hermes/](../01-runtimes/hermes/) |
| Picoclaw | Native plugin | [01-runtimes/picoclaw/](../01-runtimes/picoclaw/) |
| Claude Code | MCP stdio | [01-runtimes/claude-code/](../01-runtimes/claude-code/) |
| Cursor | MCP stdio | [01-runtimes/cursor/](../01-runtimes/cursor/) |
| Windsurf | MCP stdio | [01-runtimes/windsurf/](../01-runtimes/windsurf/) |
| Antigravity | MCP stdio | [01-runtimes/antigravity/](../01-runtimes/antigravity/) |
| Gemini agents | JSON tools / MCP | [01-runtimes/gemini/](../01-runtimes/gemini/) |
| LangChain | Codegen tool wrappers | [01-runtimes/langchain/](../01-runtimes/langchain/) |
| LangGraph | Codegen tool wrappers | [01-runtimes/langgraph/](../01-runtimes/langgraph/) |

> The full master catalog of every framework the marketplace eventually targets lives in [/root/OPVS/docs/planning/opvsHUB/MARKETPLACE-EVERYWHERE-PLAN.md](https://github.com/opvs-ai/) (internal). About 40 frameworks total; this site adds them as they ship.

For the integration pattern behind each adapter type — what code shape the runtime expects — see [03-integration-patterns/](../03-integration-patterns/).
