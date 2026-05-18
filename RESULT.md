# RESULT — opvs-ai/marketplace · redesign-A · Information architecture

**Branch:** `redesign/A-information-architecture` against `opvs-ai/marketplace:main`
**Date:** 2026-05-18
**Author session:** Claude Code IA session, single session, no sub-agents.

## What landed

The repo arrived empty (one-line README only). It now has a five-section IA covering every runtime the marketplace targets, with stubs in place but no real content.

```
/
├── README.md                        — top-level navigation
├── 00-overview/                     — three stubs (M-B)
├── 01-runtimes/                     — one section per runtime
│   ├── openclaw/                    — full subdir, reference (M-C)
│   ├── hermes/                      — full subdir (M-D)
│   ├── picoclaw/                    — full subdir (M-D)
│   ├── claude-code.md               — single file, MCP-thin (M-E)
│   ├── cursor.md                    — single file, MCP-thin (M-E)
│   ├── windsurf.md                  — single file, MCP-thin (M-E)
│   ├── antigravity.md               — single file, MCP-thin (M-E)
│   ├── gemini/                      — subdir, two install shapes (M-E)
│   ├── langchain/                   — full subdir, codegen (M-F)
│   └── langgraph/                   — full subdir, codegen (M-F)
├── 02-shared-libraries/             — three stubs (M-G)
├── 03-integration-patterns/         — four patterns (M-H)
└── reference/                       — three canonical specs (M-I)
```

Seven commits, one per section.

## Decisions made

### Subdir vs single file, per runtime

Per the brief's recommendation:

- **Subdir** for runtimes that need significant code samples: OpenClaw, Hermes, Picoclaw, Gemini, LangChain, LangGraph.
- **Single file** for MCP-thin runtimes that all point at `@opvs-ai/mcp`: Claude Code, Cursor, Windsurf, Antigravity.

### OpenClaw-family grouping

Hermes and Picoclaw live as sibling top-level directories under `01-runtimes/`, not nested under `openclaw/`. The README of `01-runtimes/` groups them visually under "OpenClaw family" but the file system stays flat. Reason: every runtime should be discoverable at the same URL depth; nesting adds clicks without buying clarity. Each Hermes / Picoclaw page references OpenClaw's equivalent as the canonical source until the audit lands.

### On-demand contract location

Two pages, cross-linked:

- `00-overview/the-on-demand-contract.md` — friendly explainer.
- `reference/on-demand-contract-spec.md` — canonical machine-readable spec.

The opvs-ai/vendors site is expected to link in to `reference/on-demand-contract-spec.md`. Single source of truth, two consumption styles.

### Number of integration patterns

Four, not three or five.

1. MCP-native
2. Plugin-based
3. Code-generation / decorator
4. API-only

Cloud agent platforms (Vertex AI, Bedrock Agents, Azure AI Studio, OpenAI Assistants) fold into API-only since they all share the "tool manifest → HTTP execute" shape. Promote to a fifth pattern if and when those integrations grow non-trivial.

### Runtime list confirmed (10 named + room for ~30 more)

The 10 from the brief — OpenClaw, Hermes, Picoclaw, Claude Code, Gemini, Cursor, Windsurf, Antigravity, LangChain, LangGraph — all have pages. No additions, no removals in this PR. Future runtimes (CrewAI, AutoGen, LlamaIndex, Pydantic AI, Mastra, Vercel AI SDK, smolagents, Letta, OpenDevin, MetaGPT, AgentGPT, Hermes-alt, Cline, Continue.dev, Zed, etc.) are flagged in `01-runtimes/README.md` and in `00-overview/pick-your-runtime.md` as the catalog-growth target.

## Open questions for planner

1. **Hermes adapter shape.** Does `github.com/NousResearch/hermes-agent` consume MCP natively? If yes, the Hermes subdir collapses into a single file like Claude Code. Audit deferred to Session D content fill-in. The IA assumes "adapter required" for now.
2. **Picoclaw entitlement enforcement.** Does Picoclaw expose `wrapApiForEntitlements`? If not, document the workaround. Audit also deferred to Session D.
3. **LangChain package split.** One combined `opvs-skills-langchain` package or per-skill split mirroring the MCP scoped packages? Recommendation in `01-runtimes/langchain/README.md` is one combined package, document the cap, split later.
4. **Gemini one page or two.** If Vertex AI Agent Builder adopts MCP across the board, the `via-function-calling.md` page is only for the bare Gemini API path. Worth considering a single-page collapse in content fill-in.
5. **Cloud platforms as fifth pattern.** Folded into `api-only-runtimes.md` for now. Worth its own pattern page later if integrations grow.
6. **MCP scoped package list.** The shared-libraries page lists six scoped packages today (`agentboard`, `agentdocs`, `agentmemory`, `opvs-protocol`, `auth`, `integrations`). The list will grow as W3 ships new skills. Either keep the page slim and point at the npm registry as the live source, or maintain an enumerated table here.
7. **Runtime catalog expansion.** Spawning sessions for the next batch of runtimes (CrewAI, AutoGen, LlamaIndex first by reach) — should those each be one PR per runtime, or a single bulk PR? Recommendation: one PR per runtime to keep diffs reviewable.

## Hard rules followed

- No real content. Every page is a stub with a `TODO` marker.
- Plain English style.
- No CI added.
- No license file added.
- One commit per section.
- No `--no-verify`.
- No force push.

## Cross-links established

- Every runtime page links into `02-shared-libraries/` for the actual package documentation.
- Every runtime page links into `00-overview/the-on-demand-contract.md` for response shape.
- Pattern pages cross-link to representative runtime examples.
- `reference/` pages are the canonical specs; `00-overview/` pages are the explainers; both point at each other.

## Next sessions

Per the brief's `M-` tags:

- M-B — Fill in `00-overview/` (three pages).
- M-C — Fill in `01-runtimes/openclaw/` (reference, 5 pages + sample-code).
- M-D — Fill in `01-runtimes/hermes/` and `picoclaw/` (audit + adapter docs).
- M-E — Fill in MCP-thin runtimes + `gemini/`.
- M-F — Fill in `01-runtimes/langchain/` and `langgraph/`.
- M-G — Fill in `02-shared-libraries/`.
- M-H — Fill in `03-integration-patterns/`.
- M-I — Fill in `reference/`.

Each is independent and can run in parallel.
