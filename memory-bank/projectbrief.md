# Project Brief — LucidLayer Documentation

## Overview
LucidLayer Docs is the public-facing developer documentation site for the LucidLayer platform — a verifiable AI inference network built on Solana. The docs are hosted on Mintlify and sourced from the `raijinlabs/docs` GitHub repo.

## Core Goals
- **Developer onboarding** — Get developers from zero to first API call in < 5 minutes
- **API reference** — Complete, auto-generated from OpenAPI spec (Speakeasy)
- **SDK documentation** — TypeScript SDK (primary), Python SDK (planned), REST reference
- **Platform guides** — Billing, API keys, metering, quotas, organizations
- **Conceptual docs** — Passports, inference, receipts, epochs, agents, MMR, Solana programs

## Target Audience
- Web3/AI developers integrating LucidLayer into their apps
- AI tool developers (MCP server integrations for Cursor, Claude Code, Windsurf)
- Platform users managing billing, API keys, and organizations

## Key Metrics
- 66 documentation pages across 6 tabs
- Auto-synced SDK docs from Speakeasy-generated sources
- OpenAPI-powered API reference

## Repository
- **Repo:** `raijinlabs/docs` on GitHub
- **Hosting:** Mintlify (auto-deploys on push to `main`)
- **Config:** `docs.json` (Mintlify configuration)
