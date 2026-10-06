# Manual submission checklist (updated 2026-10-07)

These steps need a founder login or a founder-only action. Everything that could be done from the CLI is
already done (see DIRECTORY-SUBMISSIONS.md). Paste the values exactly as written.

## Shared values

| Field | Value |
|---|---|
| Name | Assay |
| Server URL | `https://app.assay.wiki/api/mcp/v2/mcp` |
| One-liner (≤ 200) | Ranked, governed, cited GTM context for your agents, on one living source of truth. |
| Short (≤ 30, OpenAI) | Governed, cited GTM context |
| Long description | The "What Agents Can Do" section of README.md plus its governance paragraph |
| Docs | https://assay.wiki/mcp/ |
| Privacy | https://assay.wiki/legal/privacy/ |
| Terms | https://assay.wiki/legal/terms/ |
| Support | support@assay.wiki |
| Icon | `assets/assay-icon-512.png` (dark: `assets/assay-icon-512-on-dark.png`) |
| Repo (MIT) | https://github.com/Assay-Org/assay-truth-graph-mcp |
| Auth | OAuth 2.1 + PKCE S256, Dynamic Client Registration at `https://clerk.assay.wiki/oauth/register` |
| Categories | Marketing, Sales |

## 0. Prerequisite: a reviewer test account (blocks Claude, OpenAI, Docker, Glama, Smithery)

- A dedicated seat (e.g. a reviewer@ address) in a workspace on Scale or above, so write tools work.
- Truth Graph populated with sample facts (run onboarding on a demo domain, approve a handful of facts).
- No MFA, codes or magic links (OpenAI rejects those). Password sign-in only.
- Credentials go only into each portal's private reviewer field. Never into a public repo or PR.

## 1. Official MCP Registry (v0.1.0 → v0.1.2)

GitHub Actions is billing-locked, so publish from a terminal:

```bash
cd Assay-Platform/integrations/assay-truth-graph-mcp
mcp-publisher login github
mcp-publisher publish
```

Approve the device code in the browser as kloizd (Assay-Org membership must be public). PulseMCP, Glama's
connector page and MCP.Directory refresh from the registry.

## 2. Glama (free)

1. Sign in with GitHub as kloizd and claim https://glama.ai/mcp/servers/Assay-Org/assay-truth-graph-mcp
2. In Admin, add the reviewer credentials so the health check and tool-quality score can run. The connector page
   (https://glama.ai/mcp/connectors/io.github.Assay-Org/assay-truth-graph) shows "unhealthy" until then, and its
   badge is what the awesome-remote-mcp-servers PR displays.

## 3. Free web forms (no account needed)

- MCP.Directory: https://mcp.directory/submit — repo URL, one-liner, support email. Submit.
- MCP Market: https://mcpmarket.com/submit — repo URL, free queue (4-6 weeks). Don't pick the $29 option.
- mcp.so: https://mcp.so/submit — type Remote Server, repo URL, name Assay. Free queue.
- mcpservers.org: already listed (id 3344). Don't resubmit.

## 4. Claude Connectors Directory + Claude plugin directory

Portal: https://claude.ai/directory/manage (any paid claude.ai plan; the listing belongs to the org you submit from).

- **MCP connector**: Connection = universal URL above. Tools sync from the server (all carry titles and
  read-only/destructive hints). Listing fields from the table. Authentication = `oauth_dcr`. Test & launch = reviewer
  account instructions. Review the 7 compliance acknowledgments yourself.
- **Plugin bundle**: same portal, Submit new → Plugin bundle → this repo, root folder (`.claude-plugin/plugin.json`).
  Connect GitHub with push access to the repo.
- Before submitting, ship the read/write split of the 5 tools still recorded as mixed in
  `apps/webapp/src/lib/mcp/contracts/host-surface-contract.test.ts` (`outbox`, `play_control`, `sending_setup`,
  `setup_workspace`, `content_ideas`), or set `MCP_DIRECTORY_SURFACE=1` once it hides them. Anthropic's review
  rejects tools that mix safe and unsafe actions.

## 5. OpenAI plugin directory (ChatGPT + Codex, one listing)

Portal: https://platform.openai.com/plugins (org Owner, after individual or business verification in org settings).

- Display name **Assay** (names with "MCP", "Plugin" or "Server" are rejected). Short description from the table.
- Domain verification: copy the challenge token into Railway env `OPENAI_APPS_CHALLENGE_TOKEN`; the app serves it
  at `https://app.assay.wiki/.well-known/openai-apps-challenge` (route ships with cki PR #1163).
- Review packet: 5 positive + 3 negative test cases, a demo video URL, the reviewer account, release notes.
- Upload the ZIP built from `plugins/assay-truth-graph/`.

## 6. Other logins

- Smithery: https://smithery.ai/new — paste the server URL, then sign in to Assay when its scanner asks.
- Cursor Marketplace: https://cursor.com/marketplace/publish — this repo (`.cursor-plugin/plugin.json` + `mcp.json`).
- cursor.directory: sign in with GitHub → Submit a plugin → repo URL.
- Docker MCP Catalog: PR https://github.com/docker/mcp-registry/pull/5490 is open; send the reviewer account through
  https://forms.gle/6Lw3nsvu2d6nFg8e6
