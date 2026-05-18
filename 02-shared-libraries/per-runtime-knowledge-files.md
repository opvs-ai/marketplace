# Per-runtime knowledge files — `opvs-skills emit-runtime`

> Stub — TODO M-G.

## What this page will cover

The `opvs-skills emit-runtime <runtime>` command. It produces a per-runtime knowledge bundle from a brand's installed marketplace skills — a system-prompt fragment plus a structured tools manifest in whatever shape that runtime expects.

### Why this exists

Two runtime families do not consume the SDK or MCP directly:

1. **Function-calling runtimes** that expect a `functionDeclarations` array (Gemini API, OpenAI Assistants API) need that array generated from the brand's installed skills.
2. **Knowledge-driven runtimes** that expect a system prompt or "Knowledge Item" with skill instructions, paired with a tool manifest, need both produced together.

`emit-runtime` produces both.

### Outputs per runtime

| Runtime | Files emitted |
|---|---|
| `gemini` | `functions.json` + `knowledge.md` |
| `openai-assistants` | `tools.json` + `instructions.md` |
| `langchain` | `tools.py` (or `.ts`) — generated `Tool` wrappers |
| `langgraph` | Same as `langchain` |
| `vercel-ai-sdk` | `tools.ts` — generated tool defs ready for `streamText` |

### When to regenerate

When the brand's installed marketplace skills change — vendor publishes new minor, brand revokes a grant, new skill installed. Regenerate, redeploy.

The W2 ship of `opvs-skills emit-runtime` makes this a single command per runtime.

## Cross-links

- The SDK underneath: [opvs-ai-skills-sdk.md](opvs-ai-skills-sdk.md)
- The codegen integration pattern: [03-integration-patterns/code-generation-runtimes.md](../03-integration-patterns/code-generation-runtimes.md)
- The Gemini function-calling path: [01-runtimes/gemini/via-function-calling.md](../01-runtimes/gemini/via-function-calling.md)
