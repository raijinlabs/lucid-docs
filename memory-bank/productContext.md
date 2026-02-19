# Product Context — LucidLayer Documentation

## Why This Project Exists
LucidLayer is a complex platform combining AI inference, blockchain verification, and multi-tenant billing. Developers need clear, well-organized documentation to:
1. Understand core concepts (verifiable inference, passports, receipts, epochs)
2. Integrate the SDK into their applications
3. Use the API for programmatic access
4. Manage their platform account (billing, keys, quotas)

## Problems It Solves
- **Fragmented knowledge** — Centralizes all LucidLayer documentation in one place
- **SDK discoverability** — Auto-synced from Speakeasy so docs are always current
- **Developer friction** — Quickstart guides reduce time-to-first-call
- **MCP integration** — AI tool users (Cursor, Claude Code, Windsurf) can set up LucidLayer via MCP

## How It Should Work
- Mintlify renders the docs site from MDX files in this repo
- The OpenAPI spec is fetched from the SDK repo for API reference
- SDK pages are auto-rebuilt every 6 hours (or instantly via cross-repo dispatch)
- Navigation is organized into 6 tabs: Overview, Guides, API Reference, SDKs & Tools, Platform, Resources

## User Experience Goals
- Clean, searchable, fast-loading docs
- Dark/light mode with LucidLayer branding (emerald green theme)
- Code samples in TypeScript (primary) and cURL
- Clear progression: Getting Started → Concepts → Guides → API Reference
