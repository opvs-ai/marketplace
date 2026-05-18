# reference

Canonical specifications. Versioned. Stable references the rest of the site links into.

- [marketplace-api.md](marketplace-api.md) — Wire-level marketplace API. Endpoints, auth headers, response shapes, error codes.
- [on-demand-contract-spec.md](on-demand-contract-spec.md) — Canonical spec for the tool response shape every runtime sees.
- [glossary.md](glossary.md) — Terms used across the site. Brand, package, manifest, entitlement, grant, on-demand contract, partner key, trust tier.

All three pages are stubs (TODO M-I).

## Why the spec lives here, not under 00-overview

The friendly explanation of the on-demand contract lives at [00-overview/the-on-demand-contract.md](../00-overview/the-on-demand-contract.md). The canonical machine-readable spec — the thing vendors and runtime authors implement against — lives here. They cross-link.

The same split applies to the marketplace API. The "how the marketplace works" overview is in [00-overview/](../00-overview/). The endpoint table lives here.
