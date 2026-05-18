# OpenClaw — Plugin bundle format

> Stub — TODO M-C.

## What this page will cover

The wire-level shape of an OpenClaw plugin bundle as published to the marketplace.

1. **The bundle.** A signed tarball containing `index.ts`, `entitlements.ts`, `manifest.json`, and a `schema.yaml` per skill.
2. **Why `entitlements.ts` is a sibling helper.** It is not part of the index — the gateway requires both files in the extensions dir, or `index.ts` fails to load with `Cannot find module './entitlements.js'`. This is a known gotcha caught during the marketplace Phase 1 ship.
3. **The `api.registerTool` shape.** What every marketplace tool looks like in the bundle. The `parameters` field (not `inputSchema`), the `execute(toolCallId, params)` signature.
4. **Entitlement check at registration time.** How `wrapApiForEntitlements` gates each tool against the brand's granted entitlements.
5. **Signature verification.** ed25519 over the bundle tarball, verified before the gateway extracts.

## Sample code

A minimal bundle source lives at [sample-code/bundle/](sample-code/bundle/).
