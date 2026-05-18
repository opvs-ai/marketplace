# LangChain

> Stub — TODO M-F.

LangChain is the largest agentic Python framework. It expects tools declared with the `@tool` decorator or `BaseTool` subclass — not MCP, not raw plugins. The marketplace SDK generates per-skill LangChain wrappers from the same `schema.yaml` every other runtime uses.

Two language stacks ship side by side: Python (`langchain` + `langchain-community`) and JavaScript (`@langchain/core`). Same skills, same generator, two output files.

## On this page

- [install.md](install.md) — `pip install opvs-skills-langchain` or `npm install @opvs-ai/skills-langchain` plus a brand-scoped credential.
- [tools.md](tools.md) — How a marketplace skill becomes a LangChain `Tool` object.
- [auth.md](auth.md) — Where the `OPVS_PAT` env var goes and how the SDK refreshes it.
- [maintenance.md](maintenance.md) — Regenerating wrappers when the brand's installed skills change.
- [sample-code/](sample-code/) — A working LangChain agent calling a marketplace skill, end to end.

## Open question for the content fill-in author

Whether to publish one combined `opvs-skills-langchain` package or split it per skill (Wave 1 marketplace today is `@opvs-ai/mcp-agentboard`, `mcp-agentdocs`, etc. — same shape applies here).

Recommendation: start with one combined package for Python, document the cap, split if needed.
