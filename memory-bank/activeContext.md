# Active Context — LucidLayer Documentation

## Current Work Focus
- Documentation site is live and operational on Mintlify
- Auto-sync pipeline for SDK docs is fully deployed
- Logo switched from PNG to SVG to fix Mintlify S3 403 error

## Recent Changes (Feb 2026)
1. **Sprint 1:** Created initial docs structure (index, quickstart, authentication, SDK installation)
2. **Sprint 2-4:** Added 40+ pages (guides, concepts, platform, API ref, changelog)
3. **SDK docs rebuild:** Rebuilt 8 SDK pages from Speakeasy-generated sources
4. **CI/CD:** Set up GitHub Actions for auto-syncing SDK docs (6h schedule + instant dispatch)
5. **Logo fix:** Switched to SVG logos (dark.svg/light.svg) to fix S3 403 error

## Active Decisions
- **AI Tools pages** — Created as MCP integration guides for Cursor, Claude Code, and Windsurf. These show developers how to configure `@lucidlayer/mcp-server` in their AI tools. Source: created by `scripts/build-docs-sprint2-4.py`.
- **SDK auto-sync** — Every 6 hours, docs repo polls SDK repo for Speakeasy changes. Can also be triggered instantly via `DOCS_SYNC_PAT` cross-repo dispatch.

## Next Steps
- [ ] Verify Mintlify deployment with new SVG logos
- [ ] Add more detailed content to AI tools pages (currently minimal)
- [ ] Add Python SDK documentation when Python SDK is ready
- [ ] Add webhook integration guides content
- [ ] Expand API reference with more code samples
- [ ] Add interactive examples/playground

## Important Notes
- The `@lucidlayer/mcp-server` npm package referenced in AI tools pages needs to be published
- OpenAPI spec URL in docs.json points to: `https://raw.githubusercontent.com/raijinlabs/lucid-ai-sdk/main/openapi-with-code-samples.yaml`
