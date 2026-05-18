# Pattern: API-only runtimes

> Stub — TODO M-H.

## What this page will cover

The pattern. When to use it. What you write.

### The pattern

The runtime has no plugin extension point. You cannot drop a bundle into a directory, you cannot register a tool in a DSL, you cannot speak MCP. You have a model-completion call and that is it.

The marketplace is then just an HTTP API. You produce a tool manifest from `opvs-skills emit-runtime`, hand it to the model in whatever shape the model expects, and post tool calls to `/api/v1/skill_call` with a brand-scoped credential.

### What you write

- A small adapter that converts the brand's installed-skills manifest into the runtime's tool-declaration shape.
- A round-trip handler: receive a tool call from the model, post it to the marketplace, hand the response back.
- A brand-scoped auth shim (`OPVS_PAT` in env, or whatever the host platform's secret manager uses).

### What runtimes match

- The bare Gemini API with function calling (no Vertex Agent Builder).
- OpenAI Assistants API (federate with their marketplace via function tools).
- Vertex AI Agent Builder, AWS Bedrock Agents, Azure AI Studio Agents — until they adopt MCP.
- Custom in-house frameworks at enterprise customers.

### Tradeoffs

Pro: works anywhere there is an LLM call. No runtime-specific code.

Con: most glue code of any pattern. Every error case is yours. Schema changes need redeployment.

### When to promote a runtime out of this pattern

If it adopts MCP — move to [mcp-native-runtimes.md](mcp-native-runtimes.md).

If a community plugin extension point grows — move to [plugin-based-runtimes.md](plugin-based-runtimes.md) or [code-generation-runtimes.md](code-generation-runtimes.md).

## Cross-links

- The marketplace HTTP API: [reference/marketplace-api.md](../reference/marketplace-api.md)
- The emit-runtime command: [02-shared-libraries/per-runtime-knowledge-files.md](../02-shared-libraries/per-runtime-knowledge-files.md)
