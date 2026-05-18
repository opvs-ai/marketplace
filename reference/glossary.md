# Glossary

> Stub — TODO M-I.

Definitions for terms used across this site. Short and precise.

### Brand

An OPVS tenant. The unit of isolation for installs, credentials, and entitlements. Every marketplace tool call is brand-scoped.

### Package

A signed bundle a vendor publishes to `market.opvs.ai`. Wraps one or more skills.

### Skill

A logical capability — a set of related methods. One skill maps to one `schema.yaml`. Skills are how the marketplace organizes tools.

### Tool

A single callable method an agent invokes. One skill exposes many tools.

### Manifest

The JSON metadata a package ships with — name, version, dependencies, declared entitlements, schema digests.

### Entitlement

A capability declared by a package and granted by a brand at install time. Format: `vendor.<vendor>.<surface>.<verb>`. Enforced at every `registerTool` call.

### Grant

A brand's accepted entitlement set for a specific installed package. Stored in `entitlement_grants`.

### On-demand contract

The four-field response shape every marketplace tool returns. See [on-demand-contract-spec.md](on-demand-contract-spec.md).

### Partner key

A per-vendor scoped admin key used by the vendor to publish, revoke, and upload bundles. Bcrypt-hashed, prefix-lookup, vendor-scoped. Not the platform master key.

### Trust tier

One of `internal`, `beta`, `community`, `verified`. Drives how the marketplace surfaces a package and what its install UX looks like.

### Substrate tools

The eight always-on tools every runtime adapter exposes regardless of installed skills. `skill_call`, `skill_search`, `skill_describe`, `skill_pin`, `learnings_search`, `agent_handoff`, `marketplace_list_installed`, `auth_whoami`.

### Runtime

The framework or environment that hosts the AI agent — OpenClaw, Claude Code, LangChain, etc. One section of [01-runtimes/](../01-runtimes/) per runtime.

### Runtime adapter

The glue code that connects a specific runtime to the marketplace. Can be an MCP server, a native plugin, a generated SDK package, or hand-rolled HTTP.

### Doctor

The "is this skill healthy for this brand right now?" endpoint. Returns install state, entitlements, credentials, upstream health, known issues, and a single `ready: bool`.
