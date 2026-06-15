# Directory Submission Tracker

Public package path:

```text
https://github.com/Assay-Org/assay-truth-graph-mcp
```

## Listing Packet

Name: Assay Truth Graph MCP

Short description: Remote MCP server that grounds GTM agents in governed, cited
company truth.

Homepage: https://assay.wiki/

MCP page: https://assay.wiki/mcp/

Endpoint: https://app.assay.wiki/api/mcp/v2/mcp

Claude Code command:

```bash
claude mcp add --transport http assay-truth-graph https://app.assay.wiki/api/mcp/v2/mcp
```

Server config:

```json
{
  "mcpServers": {
    "assay-truth-graph": {
      "type": "http",
      "url": "https://app.assay.wiki/api/mcp/v2/mcp"
    }
  }
}
```

## Stores

| Store | Status | Notes |
|---|---|---|
| Official MCP Registry | Published / active | GitHub Actions OIDC publish succeeded: https://github.com/Assay-Org/assay-truth-graph-mcp/actions/runs/27537383906. Registry search returns `io.github.Assay-Org/assay-truth-graph` with status `active`. |
| MCP.Directory | Submitted | API response: `{"ok":true,"message":"Server submitted for review!"}`. |
| mcpservers.org / Awesome MCP Servers | Submitted | Free submission accepted with pending listing id `3344`. |
| punkpeye/awesome-mcp-servers | PR opened | https://github.com/punkpeye/awesome-mcp-servers/pull/8098 |
| Glama MCP | Prepared for ingestion | Added `glama.json` to the public repo and verified Glama search is not showing the Assay listing yet. Glama appears to ingest official registry/GitHub sources asynchronously. |
| mcp.so | Issue submitted | https://github.com/chatmcp/mcpso/issues/2817 |
| Smithery | Blocked on API key | `npx smithery@latest mcp publish ...` prompts for a Smithery API key from https://smithery.ai/account/api-keys. |
| Cline MCP Marketplace | Ready, not submitted | Issue template requires confirming Cline setup was tested from README/llms-install. Do this after a real Cline install test, then submit to https://github.com/cline/mcp-marketplace/issues/new/choose. |
| Cursor Directory | Blocked on sign-in | Submit page requires interactive account auth; public package metadata is ready. |
| MCP Market | Blocked on browser checkpoint / paid review check | Submit page is behind Vercel Security Checkpoint from this environment; do not authorize paid review without human approval. |
| PulseMCP | Awaiting crawl / blocked by Cloudflare submit page | Official registry publication should make Assay eligible for discovery; direct submit page was Cloudflare-blocked from CLI. |
| Claude Code plugin ecosystem | Ready after public repo exists | `.claude-plugin/plugin.json` and `.mcp.json` are included. |
| Claude Connectors Directory | Manual owner submission required | Remote MCP server submission requires a Claude Team/Enterprise owner flow or fallback submission form. See `MANUAL-SUBMISSION-CHECKLIST.md`. |
| ChatGPT Apps Directory | Manual Apps SDK review required | OpenAI Apps SDK review is the public path for ChatGPT Apps Directory distribution. Requires dashboard app draft, business verification, testing, and review submission. |
| Codex Plugin Directory | Prepared / review path is OpenAI Apps SDK | Added repo marketplace metadata in `.agents/plugins/marketplace.json` and `plugins/assay-truth-graph`. OpenAI docs say approved Apps SDK apps create Codex plugin distribution. |
| Replit | Install link added; curated listing route not found | Added one-click Replit install badge/link. Computer Use verified the link lands at Replit login with the MCP payload preserved. |
| Developers Digest MCP Directory | Manual / GitHub repo blocked | Submit page is https://mcp.developersdigest.tech/submit, but the linked GitHub repository returned 404 from this environment. |
| Etropo Marketing MCP Directory | Manual browser submission | Marketing-specific MCP directory with a submit path at https://www.etropo.com/marketing-mcps. Needs browser form submission. |
| MCP Server Finder | Discovery monitored | Directory exists at https://www.mcpserverfinder.com/. No reliable submit form found; GitHub topics were added to improve crawler discovery. |
| Antigravity | No public listing route found | Official site/docs pass shows MCP/plugin customization support, but no self-serve marketplace submission found. Use generic MCP config and partner outreach. |
| Emergent | No public MCP listing route found | No reliable public self-serve MCP directory submission route verified. Use partner/support outreach with the listing packet. |
| Windsurf / VS Code / similar clients | Install docs only | No public MCP directory submission route verified in this pass; use generic MCP config and public repo. |
