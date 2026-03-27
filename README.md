# FinLens Catalyst Mapper

FinLens Catalyst Mapper is a public-safe Codex plugin for turning catalysts into investable target maps across China and global markets.

## Included skills

- `FinLens Catalyst Mapper CN`: Chinese-first analysis that defaults to China macro, A-shares, and Hong Kong equities when the market is not specified.
- `FinLens Catalyst Mapper Global`: English-first analysis that defaults to U.S. equities and global macro when the market is not specified.

## What it does

- Converts events, industry shifts, supply chain disruptions, resource moves, and macro shocks into disciplined causal analysis.
- Maps the result into equities, ETFs, commodities, rates, FX, and sectors to avoid.
- Separates facts, estimates, and judgment.
- Requires timestamp and source validation before inferring from prices, macro data, policy releases, rates, FX, and valuation data.

## Public-safe design

- No local absolute paths.
- No private API keys, endpoints, or personal provider bindings.
- No claims of real-time access unless a real adapter is configured.
- Private or premium data providers are future optional adapters, not hard dependencies.

## Provider philosophy

The plugin is designed so user-specific providers stay optional. The preferred resolution order is:

1. User-configured provider that is available
2. Bundled public adapter
3. Official primary sources such as regulators, exchanges, company filings, and national statistics offices
4. High-quality financial media and recognized data sites
5. Web search fallback
6. If the fact still cannot be verified, say so clearly

Fallback is only a backup. It does not replace date, scope, unit, or source validation.

## Output behavior

- Lead with the core conclusions, then show the causal chain.
- Always connect analysis to target mapping.
- Always include timing, beneficiaries, losers, and invalidation conditions.
- Avoid fake precision, fake real-time access, and unsupported price targets.

## Repository layout

```text
finlens-catalyst-mapper/
├── .codex-plugin/
│   └── plugin.json
├── skills/
│   ├── finlens-catalyst-mapper-cn/
│   │   └── SKILL.md
│   └── finlens-catalyst-mapper-global/
│       └── SKILL.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── PRIVACY.md
├── PUBLISHING.md
├── SECURITY.md
└── TERMS.md
```

## Local install

1. Put the repository at `~/plugins/finlens-catalyst-mapper`.
2. Add or update `~/.agents/plugins/marketplace.json` so it includes:

```json
{
  "name": "finlens-catalyst-mapper",
  "source": {
    "source": "local",
    "path": "./plugins/finlens-catalyst-mapper"
  },
  "policy": {
    "installation": "AVAILABLE",
    "authentication": "ON_INSTALL"
  },
  "category": "Productivity"
}
```

3. Reload Codex so the plugin list refreshes.

## Repository docs

- `CHANGELOG.md`: release history.
- `CONTRIBUTING.md`: contribution rules for public-safe changes.
- `PRIVACY.md`: privacy posture for the public plugin.
- `PUBLISHING.md`: release checklist before pushing a public version.
- `SECURITY.md`: how to report security issues and what not to commit.
- `TERMS.md`: usage terms and analysis boundaries.

## Release status

- `plugin.json` is intentionally minimal for the public first release.
- Author, repository, homepage, website, license, privacy URL, and terms URL still need final publishing values.
- Legal and public-web fields stay explicit `TODO` values until you choose the final repo host and license.
