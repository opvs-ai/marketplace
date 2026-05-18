# OpenClaw — Auth

> Stub — TODO M-C.

## What this page will cover

How an OpenClaw gateway authenticates to the marketplace, and how each tool call is brand-scoped.

1. **Two auth paths.** Service-to-service (gateway → marketplace API) uses `X-Admin-Key`. Per-tool brand pinning uses `X-Brand-ID`.
2. **The session-key pattern.** Dashboard sessions carry `_brand_{brandId}` in the session key. Telegram or Discord agents encode the brand in `agentId` (e.g. `planner-brand-11`). The plugin reads whichever applies via `extractBrandId(ctx)` and pins it for the call.
3. **Why the brand pin matters.** Prompt-injection defense — even if an agent is tricked into requesting another brand's data, the pinned brand from the session wins over any brand param the LLM provides.
4. **Partner keys.** Vendors publish using their own scoped admin key, not the platform master key. Bcrypt-hashed, prefix-lookup, vendor-scoped on publish/revoke/upload-url.

## Cross-links

- The wire-level marketplace API: [reference/marketplace-api.md](../../reference/marketplace-api.md)
- The same auth story for MCP runtimes: [02-shared-libraries/opvs-ai-mcp.md](../../02-shared-libraries/opvs-ai-mcp.md)
