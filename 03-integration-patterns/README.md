# 03-integration-patterns

The four shapes every runtime adapter falls into. If you are adding a new runtime not covered in [01-runtimes/](../01-runtimes/), start here — pick the closest pattern and adapt.

The four patterns:

1. [mcp-native-runtimes.md](mcp-native-runtimes.md) — Runtime speaks the Model Context Protocol. Zero glue code. Examples: Claude Code, Cursor, Windsurf, Antigravity.
2. [plugin-based-runtimes.md](plugin-based-runtimes.md) — Runtime loads native TypeScript or Python plugins. Examples: OpenClaw, Hermes, Picoclaw.
3. [code-generation-runtimes.md](code-generation-runtimes.md) — Runtime expects tools in its own DSL (decorators, schema arrays). The marketplace generator emits per-runtime wrappers. Examples: LangChain, LangGraph, CrewAI, AutoGen, LlamaIndex, Pydantic AI.
4. [api-only-runtimes.md](api-only-runtimes.md) — Runtime has no plugin extension point. Treat the marketplace as a raw HTTP API and roll your own glue. Examples: bare Gemini API loop, OpenAI Assistants API, cloud agent platforms (Vertex, Bedrock, Azure).

All four pages are stubs (TODO M-H).

## Open question — should there be a fifth?

Cloud agent platforms (OpenAI Assistants API, Vertex AI Agent Builder, Bedrock Agents, Azure AI Studio) sit between code-gen and API-only. They have their own first-party marketplaces but accept function-calling tool declarations.

For now the IA folds them into `api-only-runtimes.md` since they all share the "produce a tool manifest, execute via HTTP" pattern. Promote to a fifth pattern if and when the cloud-platform integrations grow non-trivial.
