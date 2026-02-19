# SDK Docs Auto-Sync Setup

## How It Works

1. When Speakeasy regenerates the SDK in `raijinlabs/lucid-ai-sdk`, it updates `typescript/docs/`
2. A GitHub Action in the SDK repo triggers `repository_dispatch` on the docs repo
3. The docs repo runs `scripts/rebuild-sdk-docs.py` to pull fresh content
4. Changes are auto-committed and pushed → Mintlify rebuilds

## Setup Steps

### 1. Docs Repo (raijinlabs/docs) — Already Done ✅
- `scripts/rebuild-sdk-docs.py` — Fetches Speakeasy docs and builds MDX
- `.github/workflows/sync-sdk-docs.yml` — Listens for `sdk-updated` dispatch

### 2. SDK Repo (raijinlabs/lucid-ai-sdk) — You Need To Add This

Create `.github/workflows/trigger-docs-sync.yml` in the SDK repo:

```yaml
name: Trigger Docs Sync

on:
  push:
    branches: [main]
    paths:
      - 'typescript/docs/**'
      - 'typescript/README.md'
      - 'typescript/USAGE.md'
      - 'typescript/FUNCTIONS.md'

jobs:
  trigger-docs-sync:
    runs-on: ubuntu-latest
    steps:
      - name: Trigger docs repo rebuild
        uses: peter-evans/repository-dispatch@v3
        with:
          token: ${{ secrets.DOCS_SYNC_PAT }}
          repository: raijinlabs/docs
          event-type: sdk-updated
          client-payload: '{"ref": "${{ github.ref }}", "sha": "${{ github.sha }}"}'
```

### 3. Create a PAT (Personal Access Token)

1. Go to GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens
2. Create a token with:
   - **Repository access**: `raijinlabs/docs`
   - **Permissions**: Contents (read/write)
3. Add this token as a secret in the SDK repo:
   - Go to `raijinlabs/lucid-ai-sdk` → Settings → Secrets → Actions
   - Name: `DOCS_SYNC_PAT`
   - Value: The token you created

### 4. Test

Push a change to `typescript/docs/` in the SDK repo. The docs should auto-update within 2-3 minutes.

## Manual Trigger

You can also trigger a sync manually:
- Go to `raijinlabs/docs` → Actions → "Sync SDK Docs from Speakeasy" → Run workflow

## Weekly Fallback

The sync also runs every Monday at 6 AM UTC as a safety net.
