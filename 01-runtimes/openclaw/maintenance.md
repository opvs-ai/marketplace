# OpenClaw — Maintenance

> Stub — TODO M-C.

## What this page will cover

What happens after install. Versions, revocations, reloads.

1. **Version bumps.** A vendor publishes a new minor. How brands opt in (manual upgrade vs. auto-upgrade by trust tier).
2. **Revocation.** Marketplace flips `installed_packages.state` to `disabled`. The gateway picks up the flip on its 60s grant-cache TTL. No restart required.
3. **Hot reload limits.** Skill env-var changes (`moltbot.json → skills.entries.{name}.env`) need a gateway restart. The doctor merge runs at container startup only. Plain `docker compose restart` does not re-read `.env`.
4. **Doctor.** `opvs-skills doctor @vendor/skill --brand <id>` answers "can this brand use this skill, and is it healthy?" in one call.

## Cross-links

- The on-demand contract per tool response: [00-overview/the-on-demand-contract.md](../../00-overview/the-on-demand-contract.md)
- The marketplace API endpoints behind revocation: [reference/marketplace-api.md](../../reference/marketplace-api.md)
