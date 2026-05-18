# How the marketplace works

> Stub — TODO M-B. Content fill-in lands in a follow-up PR.

## What this page will cover

The end-to-end picture. Plain English, with a diagram.

1. **The registry.** `market.opvs.ai` — where vendors publish signed bundles and runtimes download them.
2. **Signed packages.** What ed25519 signing buys you (integrity, revocation, attribution) and how the gateway verifies a bundle before it loads.
3. **The install flow.** Five steps from "I want this skill" to "my agent can call this tool" — manifest pull, entitlement consent, credential grant, gateway reload, doctor check.
4. **The runtime call.** What happens when an agent invokes a marketplace tool. Where the brand pin comes from, where the credentials come from, how the response gets back to the agent.
5. **Maintenance.** Versions, revocation, the 60s grant-cache TTL, what happens when a vendor publishes a new minor.

## Where to read more

- Full reference on the wire-level marketplace API: [reference/marketplace-api.md](../reference/marketplace-api.md)
- The on-demand response contract every runtime sees: [the-on-demand-contract.md](the-on-demand-contract.md)
