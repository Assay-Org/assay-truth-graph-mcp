# Assay Truth Graph MCP

Assay Truth Graph MCP is a remote MCP server for GTM teams that need AI agents
to work from governed, cited company truth.

Assay turns positioning, proof points, brand voice, personas, collateral
context, and validation rules into a governed Truth Graph. The remote MCP server
lets Claude, ChatGPT, Cursor, Claude Code, Codex, and other MCP clients use that
context without copying company facts into each agent.

## Connect

Use the remote streamable HTTP endpoint:

```text
https://app.assay.wiki/api/mcp/v2/mcp
```

Claude Code:

```bash
claude mcp add --transport http assay-truth-graph https://app.assay.wiki/api/mcp/v2/mcp
```

Generic MCP config:

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

OAuth opens in the browser on first use for interactive clients. Headless agents
can authenticate with an org API key from Assay Settings.

## What Agents Can Do

- Get verified GTM context for customer-facing drafts.
- Search the Truth Graph with provenance and caller-aware context shaping.
- Validate draft content against approved facts and guardrails before it ships.
- Create or update Truth Graph records through dry-run and human-approved
  plan-token workflows.
- Generate grounded collateral drafts in quarantine, with preview and export
  gates.

## Links

- Product: https://assay.wiki/
- MCP docs: https://assay.wiki/mcp/
- Trust center: https://assay.wiki/trust/
- Privacy: https://assay.wiki/legal/privacy/
- Settings: https://app.assay.wiki/settings

## Directory Copy

Short description:

```text
Remote MCP server that grounds GTM agents in governed, cited company truth.
```

Tags:

```text
MCP, Model Context Protocol, remote MCP server, GTM, go-to-market, positioning,
sales enablement, content governance, AI governance, compliance, truth graph,
provenance, Claude, ChatGPT, Cursor
```

