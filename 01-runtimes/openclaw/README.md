# OpenClaw

> Native first-party runtime. The reference plugin for the marketplace. Stub — TODO M-C.

OpenClaw is OPVS' own gateway. Marketplace skills install as native TypeScript plugin bundles into the gateway's extensions directory, loaded at startup.

## On this page

- [install.md](install.md) — How to add a marketplace package to a running gateway.
- [plugin-bundle.md](plugin-bundle.md) — The bundle format. Why `entitlements.ts` is a sibling helper and not part of the index.
- [auth.md](auth.md) — Brand pinning, partner keys, the `X-Admin-Key` + `X-Brand-ID` pattern.
- [maintenance.md](maintenance.md) — Hot reload, revocation polling, the 60s grant cache.
- [sample-code/](sample-code/) — A working plugin bundle, end to end.

## TL;DR (stub content)

1. Install with `opvs-skills install @vendor/skill --brand <id>`.
2. The gateway pulls the signed bundle, verifies it, drops `index.ts` + `entitlements.ts` into `/root/.openclaw/extensions/<name>/`.
3. Restart or reload the gateway.
4. Agents on this brand see the new tools natively in their next session.

The full step-by-step lives in the per-page stubs above.
