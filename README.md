# Concord Voice Gitar configuration

Organization-wide configuration for the Gitar review agent. Every Concord Voice repository inherits it.

| Path | Purpose |
|---|---|
| `.gitar/instructions/00-org-baseline.md` | Review baseline for every repository |
| `.gitar/rules/` | Organization rules. A repository overrides one with a same-named file in its own `.gitar/rules/` |
| `.gitar/skills/` | Skills that run only when named: `gitar run the <name> skill on this` |
| `.gitar/config/approve.md` | Auto-approve criteria. Repositories may add stricter criteria |
| `.gitar/config/risk.md` | Risk levels |

The organization's instruction budget is 32 KB across all layers, so keep these files short. Repository-specific guidance lives in each repository's `.gitar/review/`.

Changes need security code-owner review.
