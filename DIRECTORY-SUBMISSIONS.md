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
| Official MCP Registry | Workflow staged | `server.json` validates locally and with `mcp-publisher validate`; publish workflow uses GitHub Actions OIDC. |
| MCP.Directory | Submitted | API response: `{"ok":true,"message":"Server submitted for review!"}`. |
| mcp.so | Blocked on sign-in | API returned `{"code":-1,"message":"no auth, please login"}` after posting prepared payload. |
| Smithery | Needs public repo review | Check whether remote-only entries are accepted before submitting. |
| Glama MCP | Needs public repo or registry ingestion | Likely indexable after official registry publication. |
| Cline MCP Marketplace | Needs repo/PR path review | Public repo metadata can be reused if remote servers are accepted. |
| Claude Code plugin ecosystem | Ready after public repo exists | `.claude-plugin/plugin.json` and `.mcp.json` are included. |
