# Pattern: Code-generation runtimes

> Stub — TODO M-H.

## What this page will cover

The pattern. When to use it. What you write.

### The pattern

The runtime expects tools declared in its own DSL — Python decorators, TypeScript builder functions, JSON schema arrays. The marketplace cannot ship one binary that works in every framework. Instead the marketplace SDK generates per-skill wrappers from the same `schema.yaml`, one output file per runtime.

The user installs a small package (e.g. `pip install opvs-skills-langchain`) and gets a typed object per skill, ready to wire into their agent code.

### What you write

- A generator target in `packages/opvs-skills/src/generators/` that takes a `schema.yaml` and emits code in the runtime's expected shape.
- A small per-runtime package that bundles those emissions plus an executor that talks to the marketplace HTTP API.
- Documentation for both regeneration (when brand's installed skills change) and pinning.

### What runtimes match

- LangChain (Python and JS).
- LangGraph (Python and JS) — same emitter as LangChain.
- CrewAI, AutoGen, LlamaIndex, Pydantic AI, DSPy, Semantic Kernel, smolagents, ControlFlow.
- Vercel AI SDK and Mastra (Node frameworks consuming the typed SDK directly fall here too, even though they do not need codegen).

### Tradeoffs

Pro: feels native inside each framework. Developers get the shape they already know.

Con: per-runtime build pipeline. Schema changes force a regenerate. Pinning matters.

### The emit-runtime command

`opvs-skills emit-runtime <runtime> --brand <id>` produces the files. Re-run whenever the brand's installed skills change.

## Cross-links

- The SDK contract every emission wraps: [02-shared-libraries/opvs-ai-skills-sdk.md](../02-shared-libraries/opvs-ai-skills-sdk.md)
- The emit-runtime command: [02-shared-libraries/per-runtime-knowledge-files.md](../02-shared-libraries/per-runtime-knowledge-files.md)
- LangChain reference: [01-runtimes/langchain/](../01-runtimes/langchain/)
