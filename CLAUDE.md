# Lucid Documentation

## What This Is
Official developer documentation for the Lucid verifiable AI inference platform. Built with Mintlify, auto-deployed on push to `main`.

## Quick Start
```bash
npm i -g mintlify
mintlify dev          # Local preview
```

## Structure (49 pages, 5 tabs)
```
Root:           index, quickstart, authentication, sdk-installation, architecture, glossary
concepts/       passports, inference, receipts, epochs, agents, mmr, solana-programs, session-signer, trustgate, mcpgate
guides/         first-inference, passport-management, error-handling, verifiable-receipts, epoch-verification,
                agent-orchestration, streaming, compute-providers, hf-passport-sync, n8n-integration,
                nango-oauth, crewai-integration, self-hosting, webhooks
api-reference/  introduction, errors, rate-limits + auto-generated from OpenAPI spec
sdks/           typescript (+ passports/inference/receipts/agents sub-pages), python, rest, mcp-server
platform/       billing, api-keys, metering, quotas, organizations, dashboard, security, sla
```

## Config
- `docs.json` — Mintlify v2 config (Aspen theme, Montserrat font)
- OpenAPI source: `github.com/raijinlabs/lucid-ai-sdk/main/openapi-with-code-samples.yaml`
- SDK docs sync: GitHub Actions, every 6 hours, `scripts/rebuild-sdk-docs.py`

## Branding
- Primary color: `#6366F1` (indigo)
- Dashboard: `app.lucid.foundation`
- API: `api.lucid.foundation`
- SDK: `raijin-labs-lucid-ai` (npm)

## Current Status
100% content complete. All 49 pages have substantive content. API endpoints auto-generated from OpenAPI spec.

## Remote
`github.com/raijinlabs/lucid-docs.git` — branch: `main`, auto-deploy via Mintlify GitHub App
