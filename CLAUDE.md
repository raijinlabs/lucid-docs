# Lucid Documentation

## What This Is
Official developer documentation for the Lucid verifiable AI inference platform. Built with Mintlify, auto-deployed on push to `main`.

## Quick Start
```bash
npm i -g mintlify
mintlify dev          # Local preview
```

## Structure (~66 pages, 6 tabs)
```
index.mdx, quickstart.mdx, architecture.mdx, glossary.mdx
concepts/       # passports, inference, receipts, epochs, agents, mmr, solana-programs
guides/         # first-inference, streaming, n8n-integration, crewai, self-hosting, webhooks
api-reference/  # Auto-generated from OpenAPI spec
sdks/           # TypeScript, Python, REST, MCP server
platform/       # billing, api-keys, metering, quotas, organizations, security
```

## Config
- `docs.json` — Mintlify v2 config
- OpenAPI source: `github.com/raijinlabs/lucid-ai-sdk/main/openapi-with-code-samples.yaml`
- SDK docs sync: GitHub Actions, every 6 hours, `scripts/rebuild-sdk-docs.py`

## Branding
- Primary color: `#6366F1` (indigo)
- Dashboard: `app.lucid.foundation`
- API: `api.lucid.foundation`
- SDK: `raijin-labs-lucid-ai` (npm)

## Current Status
~15% content complete. Infrastructure fully deployed. Some pages still use Mintlify starter defaults.

## Remote
`github.com/raijinlabs/lucid-docs.git` — branch: `main`, auto-deploy via Mintlify GitHub App
