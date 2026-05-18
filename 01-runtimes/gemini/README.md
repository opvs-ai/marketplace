# Gemini

> Stub — TODO M-E. Subdir because Gemini-based agents have two install shapes — MCP and native function calling.

Gemini-based agent runtimes include Vertex AI Agent Builder, the standalone Gemini API with function calling, and the `gemini-cli` family. The marketplace integration shape depends on which you run.

## On this page

- [via-mcp.md](via-mcp.md) — If your Gemini runtime speaks MCP, this is the simpler path. Mostly an install snippet pointing at `@opvs-ai/mcp`.
- [via-function-calling.md](via-function-calling.md) — If your runtime expects Google's function-calling JSON shape (declarations array, plus a Knowledge Items / system-prompt bundle), use this path.
- [sample-code/](sample-code/) — Both shapes, runnable.

## Open question for the content fill-in author

Decide whether to merge these two pages or keep them separate. Two pages is cleaner if Vertex AI ends up using MCP — then `via-function-calling.md` is only for the bare Gemini API path.
