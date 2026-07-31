# Assay Truth Graph MCP

Assay Truth Graph MCP is a remote MCP server for GTM teams that need AI agents
to work from governed, cited company truth.

Assay turns positioning, proof points, brand voice, personas, collateral
context, and validation rules into a governed Truth Graph. The remote MCP server
hands that context to Claude, ChatGPT, Cursor, Claude Code, Codex, and other MCP
clients without copying company facts into each agent.

The server has full parity with the Assay app. What the team does in the
product, your agents can do here: 48 registered tools spanning Truth Graph
search and governed mutation, content validation, collateral, AI search and
GEO, readiness simulation, pre-call briefs, and review and promotion. Call
`tools/list` on the live endpoint for the current surface.

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

Replit one-click install:

[![Install in Replit](https://replit.com/badge?caption=Install%20in%20Replit)](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFzc2F5IFRydXRoIEdyYXBoIE1DUCIsImJhc2VVcmwiOiJodHRwczovL2FwcC5hc3NheS53aWtpL2FwaS9tY3AvdjIvbWNwIn0)

Codex repo marketplace:

```bash
codex plugin marketplace add Assay-Org/assay-truth-graph-mcp
```

Then install the `Assay Truth Graph` plugin from Codex Plugins.

## What Agents Can Do

- Get verified GTM context for customer-facing drafts.
- Search the Truth Graph with provenance and caller-aware context shaping.
- Validate draft content against approved facts and guardrails before it ships.
- Create or update Truth Graph records through dry-run and human-approved
  plan-token workflows.
- Generate grounded collateral drafts in quarantine, with preview and export
  gates, and re-render them when the underlying story changes.
- Run the AI search and GEO workspace: briefs, artifacts, evidence, goals,
  hosted sites, and approval-gated publishing.
- Run readiness simulations and build pre-call briefs.
- Review, approve, and promote through the same gates the app uses.

Two entitlement lanes are enforced server-side. `mcp_access` covers read and
verification tools on Free and above. `mcp_control_access` covers write and run
tools on Scale and above. Writes are dry-run by default and mint a single-use,
expiring plan token that must be confirmed. Pricing, policy, proof, and identity
kinds are refused for autonomous mutation, and unmapped kinds fail closed.

## Links

- Product: https://assay.wiki/
- MCP docs: https://assay.wiki/mcp/
- Trust center: https://assay.wiki/trust/
- Privacy: https://assay.wiki/legal/privacy/
- Settings: https://app.assay.wiki/settings
- Manual listing checklist: ./MANUAL-SUBMISSION-CHECKLIST.md
- Directory tracker: ./DIRECTORY-SUBMISSIONS.md

## Directory Copy

Short description (standard field):

```text
Ranked, governed, cited GTM context for your agents, on one living source of truth.
```

Short description (hard short limits, 47 chars):

```text
Governed, cited GTM context for your AI agents.
```

Company one-liner (about-the-company slots):

```text
Elite AI GTM team on one living source of truth.
```

Tags:

```text
MCP, Model Context Protocol, remote MCP server, GTM, go-to-market, marketing,
sales, content, SEO, brand, positioning, messaging, sales enablement,
content governance, AI governance, compliance, truth graph, provenance,
knowledge graph, Claude, ChatGPT, Cursor
```
