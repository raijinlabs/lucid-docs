# Tech Context — LucidLayer Documentation

## Technologies Used
- **Mintlify** — Documentation platform (renders MDX, hosts site, provides search)
- **MDX** — Markdown with JSX components for rich documentation
- **GitHub Actions** — CI/CD for auto-syncing SDK docs
- **Speakeasy** — SDK generation tool (generates TypeScript SDK + docs from OpenAPI)
- **OpenAPI 3.x** — API specification format for auto-generated API reference
- **Python scripts** — Build/sync automation (rebuild-sdk-docs.py, etc.)

## Development Setup
```bash
# Clone the repo
git clone https://github.com/raijinlabs/docs.git
cd docs

# Install Mintlify CLI (optional, for local preview)
npm install -g mintlify

# Start local dev server
mintlify dev

# Rebuild SDK docs manually
python scripts/rebuild-sdk-docs.py
```

## Key Configuration Files
| File | Purpose |
|------|---------|
| `docs.json` | Mintlify config: navigation, theme, colors, logo, OpenAPI source |
| `.github/workflows/sync-sdk-docs.yml` | CI workflow for auto-syncing SDK docs |
| `scripts/rebuild-sdk-docs.py` | Python script to fetch + build SDK MDX pages |

## Dependencies
- **External:** Mintlify hosting, GitHub, Speakeasy (via lucid-ai-sdk repo)
- **Internal:** `raijinlabs/lucid-ai-sdk` (OpenAPI spec + Speakeasy docs source)

## Technical Constraints
- Mintlify has specific MDX component support (not all JSX works)
- OpenAPI spec must be publicly accessible URL for API playground
- Logo/images must be in repo (Mintlify serves from its S3, but relative paths work best)
- Maximum ~200 pages before navigation becomes unwieldy

## Repo Secrets
| Secret | Repo | Purpose |
|--------|------|---------|
| `DOCS_SYNC_PAT` | `lucid-ai-sdk` | Cross-repo dispatch to trigger docs rebuild |
