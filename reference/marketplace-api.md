# Marketplace API — reference

> Stub — TODO M-I.

## What this page will cover

Every wire-level endpoint a runtime adapter or vendor tool talks to. Grouped by surface.

### Registry (public reads)

- `GET /api/v1/registry/packages` — List published packages.
- `GET /api/v1/registry/packages/{vendor}/{name}` — Package detail.
- `GET /api/v1/registry/packages/{vendor}/{name}/versions` — Version history.
- `GET /api/v1/registry/manifest` — Full manifest for gateway revocation polls.

### Install lifecycle

- `POST /api/v1/marketplace/packages/{package_id}/install` — Five-step install wizard endpoint.
- `GET /api/v1/marketplace/installed/{install_id}` — Per-brand install state.
- `PATCH /api/v1/marketplace/installed/{install_id}/entitlements` — Grant or revoke.
- `PATCH /api/v1/marketplace/installed/{install_id}/agents` — Per-agent opt-out.
- `DELETE /api/v1/marketplace/installed/{install_id}` — Uninstall (fan-outs `package.uninstalled`).

### Skill call (the on-demand call site)

- `POST /api/v1/skill_call` — The unified entry point every runtime adapter posts to. Body shape, response shape, error codes all live here.

### Doctor

- `GET /api/v1/skills/{skill_id}/doctor` — "Can this brand use this skill, and is it healthy?"

### Auth

- Header `X-Admin-Key` or `Authorization: Bearer <PAT>`.
- Header `X-Brand-ID` is mandatory on admin-key calls, set automatically on session-auth calls.

## Cross-links

- The internal main-API surface: see `/root/OPVS/CLAUDE.md` (internal — full endpoint inventory and gotchas).
- The vendor publish surface: [opvs-ai/vendors](https://github.com/opvs-ai/vendors).
