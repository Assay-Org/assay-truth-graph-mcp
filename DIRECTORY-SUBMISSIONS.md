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
| mcp.so | Blocked on sign-in | API returned `{"code":-1,"message":"no auth, please login"}` after posting prepared payload. |
| Smithery | Blocked on API key | `npx smithery@latest mcp publish ...` prompts for a Smithery API key from https://smithery.ai/account/api-keys. |
| Cline MCP Marketplace | Ready, not submitted | Issue template requires confirming Cline setup was tested from README/llms-install. Do this after a real Cline install test, then submit to https://github.com/cline/mcp-marketplace/issues/new/choose. |
| Cursor Directory | Blocked on sign-in | Submit page requires interactive account auth; public package metadata is ready. |
| MCP Market | Blocked on browser checkpoint / paid review check | Submit page is behind Vercel Security Checkpoint from this environment; do not authorize paid review without human approval. |
| PulseMCP | Awaiting crawl / blocked by Cloudflare submit page | Official registry publication should make Assay eligible for discovery; direct submit page was Cloudflare-blocked from CLI. |
| Claude Code plugin ecosystem | Ready after public repo exists | `.claude-plugin/plugin.json` and `.mcp.json` are included. |
