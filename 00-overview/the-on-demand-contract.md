# The on-demand contract

> Stub — TODO M-B. Content fill-in lands in a follow-up PR. Canonical spec lives in [reference/on-demand-contract-spec.md](../reference/on-demand-contract-spec.md); this page is the friendly explainer.

## What this page will cover

Every marketplace tool, regardless of runtime, returns the same response shape. This page explains that shape in plain English so a developer building a new runtime adapter knows what to wrap.

Topics:

1. **The four sibling fields.** `result`, `_guidance`, `_findings` (optional), `telemetry_signal` (enum). Why each one exists. How the runtime should present each to the agent or the user.
2. **`intent` over `query`.** The naming convention all marketplace tools follow on input. Why a runtime adapter should not silently rename it.
3. **What "on-demand" means.** The agent does not need to learn 200 tools upfront. It learns one substrate tool (`skill_call`) plus a small discovery surface. Tools materialize when called.
4. **The substrate tools every runtime should expose.** Eight always-on tools: `skill_call`, `skill_search`, `skill_describe`, `skill_pin`, `learnings_search`, `agent_handoff`, `marketplace_list_installed`, `auth_whoami`.
5. **Compatibility notes per runtime family.** MCP runtimes get this shape natively. Plugin runtimes wrap the response into their plugin's return type. Codegen runtimes generate per-tool Python or TypeScript wrappers that preserve the shape.

## Cross-links

- Canonical wire spec: [reference/on-demand-contract-spec.md](../reference/on-demand-contract-spec.md)
- The same contract from the vendor side: [opvs-ai/vendors](https://github.com/opvs-ai/vendors) — schema authoring guide.
