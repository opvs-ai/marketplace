# Picoclaw

> Stub — TODO M-D. Picoclaw is a lightweight OpenClaw variant.

Picoclaw shares OpenClaw's plugin convention but trims the runtime to a smaller footprint. The marketplace bundle format is the same; the install paths differ.

## On this page

- [install.md](install.md) — Picoclaw extensions directory layout.
- [plugin-bundle.md](plugin-bundle.md) — Same bundle shape as OpenClaw. Note any trimmed API surface.
- [auth.md](auth.md) — Brand-scoped auth.
- [maintenance.md](maintenance.md) — Reload model.
- [sample-code/](sample-code/) — A working Picoclaw plugin.

## Open question for the content fill-in author

Confirm Picoclaw exposes `api.registerTool` and `wrapApiForEntitlements`. If it strips entitlements, document the workaround.
