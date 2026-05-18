# Hermes

> Stub — TODO M-D. Hermes is `github.com/NousResearch/hermes-agent`.

Hermes is a NousResearch agent runtime. Mirror the OpenClaw plugin shape with whatever tweaks Hermes' tool-registration model demands.

## On this page

- [install.md](install.md) — How to add a marketplace package to Hermes.
- [plugin-bundle.md](plugin-bundle.md) — Adapter from the marketplace bundle to Hermes' tool format.
- [auth.md](auth.md) — Brand-scoped auth in Hermes.
- [maintenance.md](maintenance.md) — Version bumps and revocation.
- [sample-code/](sample-code/) — A working Hermes plugin, end to end.

## Open question for the content fill-in author

Step 1 of the content session: clone `github.com/NousResearch/hermes-agent`. Decide whether Hermes consumes MCP natively.

- If yes: this page becomes mostly install instructions pointing at `@opvs-ai/mcp`, like the MCP-thin runtimes. The other four pages collapse into one.
- If no: keep the five-page shape. Write the adapter.

The IA assumes "adapter required" until the audit says otherwise.
