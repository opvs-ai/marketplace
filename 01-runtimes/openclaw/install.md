# OpenClaw — Install

> Stub — TODO M-C.

## What this page will cover

The exact steps to install a marketplace package into a running OpenClaw gateway.

1. Pick the package. Browse `market.opvs.ai` or call the registry API.
2. Run `opvs-skills install @vendor/skill --brand <brand-id>`.
3. Approve entitlements (interactive prompt or `--accept-entitlements` flag).
4. Grant credentials, if the package requires any. Either paste a token or trigger the credential-invite flow.
5. Watch the gateway logs to confirm the bundle loaded.
6. Verify with `opvs-skills doctor @vendor/skill`.

Includes a diagram of the install pipeline (CLI → registry → install endpoint → gateway → grant cache).

## Sample code

A real install transcript lives at [sample-code/install.sh](sample-code/install.sh).
