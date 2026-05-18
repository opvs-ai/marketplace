# LangGraph

> Stub — TODO M-F.

LangGraph is LangChain's graph-based agent orchestration layer. Tools are declared identically to LangChain — the marketplace integration is largely a copy of [01-runtimes/langchain/](../langchain/), with extra notes on how to call marketplace skills from inside graph nodes.

## On this page

- [install.md](install.md) — Same package as the LangChain integration; same install steps.
- [tools.md](tools.md) — How a marketplace skill becomes a node-callable tool.
- [auth.md](auth.md) — Same `OPVS_PAT` env-var pattern.
- [maintenance.md](maintenance.md) — Regenerating wrappers.
- [sample-code/](sample-code/) — A working graph with one marketplace skill in one of the nodes.

## Open question for the content fill-in author

Whether LangGraph deserves a separate package or can ride on the LangChain SDK with documentation pointing here. Recommendation: same package, separate docs.
