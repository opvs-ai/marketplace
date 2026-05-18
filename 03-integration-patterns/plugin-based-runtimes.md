# Pattern: Plugin-based runtimes

> Stub — TODO M-H.

## What this page will cover

The pattern. When to use it. What you write.

### The pattern

The runtime loads native plugins from a known extensions directory. Plugins declare tools through the runtime's own registration API. The marketplace ships a signed bundle that drops into the extensions directory; the runtime loads it at startup.

### What you write

- A bundle exporter for the runtime's expected plugin shape.
- A sibling helper file (`entitlements.ts` in OpenClaw's case) for any cross-cutting concerns the bundle imports.
- A signed manifest with the bundle.
- Documentation telling brands where the extensions directory lives.

### What runtimes match

- OpenClaw (reference).
- Hermes and Picoclaw (OpenClaw-family, share most of the shape).
- Future first-party runtimes built on the same Node.js plugin convention.

### Tradeoffs

Pro: native tool integration, no MCP-stdio process overhead, tools appear as first-class functions in the agent's LLM context.

Con: per-runtime build pipeline, signature verification mandatory, hot-reload semantics vary by runtime.

### Known gotchas

- **Bundle sibling helpers must be co-located.** The OpenClaw bundle fails to load with `Cannot find module './entitlements.js'` if `entitlements.ts` is missing.
- **Plugin tool schema field is `parameters`, not `inputSchema`.** Wrong field name crashes the gateway on load.
- **OpenAI tool-name regex `^[a-zA-Z0-9_-]+$`.** Dotted names break runtimes calling OpenAI-routed models. Document for every plugin-based runtime that might route to OpenAI.

## Cross-links

- The OpenClaw reference: [01-runtimes/openclaw/plugin-bundle.md](../01-runtimes/openclaw/plugin-bundle.md)
