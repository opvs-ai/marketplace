# Gemini — via native function calling

> Stub — TODO M-E.

If your Gemini runtime expects Google's native function-calling JSON shape (a `functionDeclarations` array plus a Knowledge-Items / system-prompt bundle), use this path.

## What this page will cover

1. **Generate the declarations.** `opvs-skills emit-runtime gemini --brand <id>` produces a `functions.json` + `knowledge.md` pair for the brand's installed skills.
2. **Wire the declarations into your Gemini call.** Show the canonical Python and Node snippets — `genai.GenerativeModel(..., tools=[Tool(function_declarations=...)])`.
3. **Execute tool calls.** When the model returns a `function_call`, post it to the marketplace HTTP API (`/api/v1/skill_call`) with a brand-scoped credential. The response shape is the on-demand contract — return it back to the model as a `function_response`.
4. **Maintenance.** When the brand's installed skills change, re-run `opvs-skills emit-runtime gemini` and redeploy the declarations.
5. **Sample code.** A minimal Python loop end to end.

## Cross-links

- The emit-runtime command: [02-shared-libraries/per-runtime-knowledge-files.md](../../02-shared-libraries/per-runtime-knowledge-files.md)
- The on-demand contract: [00-overview/the-on-demand-contract.md](../../00-overview/the-on-demand-contract.md)
- The marketplace HTTP API: [reference/marketplace-api.md](../../reference/marketplace-api.md)
