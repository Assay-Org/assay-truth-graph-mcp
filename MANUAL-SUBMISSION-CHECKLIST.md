# Manual Submission Checklist

Use this checklist for listing paths that require a human owner login, API key
creation, CAPTCHA/checkpoint, or a final form submission from an Assay account.

## Listing Packet

Name: Assay Truth Graph MCP

Short description: Remote MCP server that grounds GTM agents in governed, cited
company truth.

Endpoint: https://app.assay.wiki/api/mcp/v2/mcp

Docs: https://assay.wiki/mcp/

Repo: https://github.com/Assay-Org/assay-truth-graph-mcp

Company site: https://assay.wiki/

Privacy policy: https://assay.wiki/legal/privacy/

Terms: https://assay.wiki/legal/terms/

Support email: hello@assay.wiki

Logo URL: https://assay.wiki/assay-brand-assets/png/assay-icon-dark-256x256.png

Suggested categories: GTM, sales enablement, knowledge, memory, governance,
content governance, AI governance.

## Claude Connectors Directory

1. Sign in to Claude with a Team or Enterprise workspace owner account.
2. Open https://claude.ai/new?admin=mcp-directory.
3. Choose remote MCP server / connector submission.
4. Enter the listing packet above.
5. Set authentication to OAuth for interactive users.
6. Provide test credentials or a demo workspace with sample Truth Graph data.
7. Confirm the server has been tested in Claude or MCP Inspector.
8. Submit for review and watch the account email for review follow-up.

## ChatGPT Apps Directory and Codex Plugin Directory

OpenAI currently uses the Apps SDK review path for both ChatGPT app listing and
Codex plugin directory distribution.

1. Sign in to https://platform.openai.com with an Assay organization owner or a
   user with app write permissions.
2. Complete business verification in the organization settings for the Assay
   publisher name.
3. Create an Apps SDK app draft in https://platform.openai.com/apps-manage.
4. Connect the production MCP server at
   `https://app.assay.wiki/api/mcp/v2/mcp`.
5. Add app metadata, tool descriptions, privacy policy, terms, support contact,
   icon, and any required ChatGPT UI component metadata.
6. Test the app in ChatGPT developer mode with direct, indirect, and negative
   prompts.
7. Provide a fully featured demo account with sample data if the review form
   requests one.
8. Submit the app for review. If approved, OpenAI creates the corresponding
   Codex plugin directory distribution.

Repo-side Codex support is already included here through `.agents/plugins` and
`plugins/assay-truth-graph`; users can add this repo as a Codex plugin
marketplace while the public review flow is pending.

## Replit

1. Open the install link:
   https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkFzc2F5IFRydXRoIEdyYXBoIE1DUCIsImJhc2VVcmwiOiJodHRwczovL2FwcC5hc3NheS53aWtpL2FwaS9tY3AvdjIvbWNwIn0
2. Sign in to Replit.
3. Continue through the integration prompt.
4. Authorize Assay Truth Graph MCP for the target Replit workspace/project.
5. Verify Replit Agent can see and call the Assay MCP tools.

Replit's public docs expose one-click install links and a curated MCP list, but
no public self-serve form for curated list submission was found in this pass.

## Smithery

1. Sign in to https://smithery.ai.
2. Open https://smithery.ai/account/api-keys.
3. Create a short-lived API key.
4. Provide the key to the publishing shell when ready.
5. Run:

```bash
npx -y smithery@latest mcp publish \
  "https://app.assay.wiki/api/mcp/v2/mcp" \
  -n "Assay-Org/assay-truth-graph" \
  --json
```

## Cursor

1. Sign in to Cursor.
2. Open the Cursor MCP/directory submission flow.
3. Paste the listing packet above.
4. Use the generic MCP config from `README.md`.
5. Submit from the signed-in account.

## Cline MCP Marketplace

1. Install Cline and add Assay using the generic MCP config from `README.md`.
2. Verify Cline can connect and list the server tools.
3. Open https://github.com/cline/mcp-marketplace/issues/new/choose.
4. Choose the MCP server submission template.
5. Fill in the listing packet and confirm the install test was completed.
6. Submit the issue.

## MCP Market and PulseMCP

1. Open the marketplace submit page in a logged-in browser.
2. Complete any browser checkpoint or CAPTCHA yourself.
3. Paste the listing packet above.
4. Do not approve paid review or paid promotion without an explicit budget.
5. Submit and save the confirmation URL or email.

## Antigravity, Emergent, Windsurf, VS Code, and Similar Clients

No public self-serve MCP directory submission route was verified for these
surfaces during the June 15, 2026 pass. For now, use the generic MCP config from
`README.md` and pursue partner/support outreach with the listing packet above.
