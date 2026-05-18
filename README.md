# OPVS Marketplace — Runtime Distributions

This site is for developers and teams running AI agents who want to install OPVS Marketplace skills into the runtime they already use.

You picked OpenClaw, Hermes, Claude Code, Cursor, LangChain, or one of about twenty other runtimes. Find your runtime here and follow the install guide.

## Start here

- [00-overview/](00-overview/) — How the marketplace works, what every runtime sees in a tool response, and a runtime picker table.
- [01-runtimes/](01-runtimes/) — One section per runtime. Install, plug in, authenticate, call tools, keep up to date.
- [02-shared-libraries/](02-shared-libraries/) — The npm packages and emitted knowledge files most runtimes share.
- [03-integration-patterns/](03-integration-patterns/) — The four shapes runtime integrations take.
- [reference/](reference/) — Marketplace API spec, on-demand contract spec, glossary.

## Two related sites

This site covers the **demand side** — runtimes consuming the marketplace.

For the **supply side** — vendors publishing packages — see [opvs-ai/vendors](https://github.com/opvs-ai/vendors). Onboarding, signing keys, the manifest spec, and the publish flow live there.

The legacy file-based skill source at [martinshein/opvsHUB](https://github.com/martinshein/opvsHUB) is frozen. Do not add new content there.

## Status

This repo is being built up in two phases.

1. **Information architecture** — directory layout, README skeletons, per-runtime stubs. (Current phase.)
2. **Content fill-in** — real install guides, sample code, screenshots, troubleshooting. One PR per section.

If a page is a stub it will say so at the top.
