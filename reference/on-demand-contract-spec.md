# On-demand contract — canonical spec

> Stub — TODO M-I. Canonical spec. Friendly explainer lives at [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md).

## What this page will cover

The wire-level shape every marketplace tool response conforms to. The spec runtime authors and vendors implement against.

### Response shape

```json
{
  "result": {},
  "_guidance": "string",
  "_findings": {},
  "telemetry_signal": "success | partial | rate_limit | upstream_error | auth_error | unknown"
}
```

- `result` — required. The skill's actual return value.
- `_guidance` — required. Short prose, what the agent should know after this call. Sibling field on the response, not nested inside `result`.
- `_findings` — optional. Structured side-channel info (warnings, deprecations, soft errors).
- `telemetry_signal` — required. One of the enum values above. Drives doctor and entitlement-health metrics.

### Input shape

Every marketplace tool accepts `intent` as the first-class param. Some skills take a verbatim `query`; those skills explicitly document the difference. A runtime adapter MUST NOT silently rename `intent` to `query`.

### The eight substrate tools

Every runtime adapter is expected to expose these as always-on:

| Tool | Purpose |
|---|---|
| `skill_call` | Universal dispatcher. `{ skill, method, params }`. Returns the on-demand shape. |
| `skill_search` | Discovery. Returns skill candidates with summaries. |
| `skill_describe` | Detail. Full schema for one skill. |
| `skill_pin` | Pin a skill to the session for repeated use. |
| `learnings_search` | Search the brand's learnings store. |
| `agent_handoff` | Delegate to another OPVS agent. |
| `marketplace_list_installed` | List what is installed for this brand. |
| `auth_whoami` | Identity introspection. |

### Versioning

This contract is currently at v1. Breaking changes bump the major. Adding optional fields is non-breaking.

## Cross-links

- The friendly explainer: [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md).
- The marketplace API: [marketplace-api.md](marketplace-api.md).
- The vendor side of the same contract: [opvs-ai/vendors](https://github.com/opvs-ai/vendors) — schema authoring.
