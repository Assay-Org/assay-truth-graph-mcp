# Directory Submission Tracker

Public package path:

```text
https://github.com/Assay-Org/assay-truth-graph-mcp
```

## Listing Packet

Name: Assay Truth Graph MCP

Short description (standard field): Ranked, governed, cited GTM context for your
agents, on one living source of truth.

Short description (hard short limits, 47 chars): Governed, cited GTM context for
your AI agents.

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

## Submission notes: the read/write split (2026-10-06)

Reviewers (Claude directory, ChatGPT apps) look at tool hints, so the listed
surface is split by effect:

- `assay` is `readOnlyHint: true`, `openWorldHint: false`. Its only rows are
  call telemetry. Always loaded in Claude Code.
- `assay_act` is `readOnlyHint: false`, `destructiveHint: false`. Every action
  previews first and executes only with a single-use plan token after the user
  agrees; confirming context and lead preferences need a signed-in person
  (OAuth), never an API key.
- The existing tools keep their names and contracts. Workspaces can later get a
  shorter tool list per seat (standard, editor, admin); a tool leaving a seat's
  list keeps working for one release and says so in its response.
- Rate limits: per credential before auth, and per workspace after auth (2,000
  tool calls a minute in total, 600 per tool).

Update the Glama listing and the Claude directory submission with this split and
the README's front-door section in the same release that ships it.

## Stores

| Store | Status | Notes |
|---|---|---|
| Official MCP Registry | Content updated 2026-07-31, republish pending | `server.json` v0.1.1 pushed to `main` (commit `d3568af`) and tag `v0.1.1` pushed. The repo's own OIDC auto-publish workflow (`publish-mcp.yml`) triggered on the tag push but failed immediately: **"your account is locked due to a billing issue"** on the GitHub org — a pre-existing, unrelated Actions billing problem (see project memory `ci-actions-minutes-exhausted-2026-06-07`), not a content or workflow defect. Worked around by running `mcp-publisher login github` directly (device-code flow) to publish without Actions. |
| MCP.Directory | Submitted (June) | API response: `{"ok":true,"message":"Server submitted for review!"}`. Not re-verified this session; description there is presumably still the pre-2026-07-31 copy. |
| mcpservers.org / Awesome MCP Servers | Already submitted (June), listing id `3344` — **do not resubmit** | Free submission accepted in June. Resubmitting risks a duplicate/spam listing. The live listing almost certainly still shows the old description; updating it requires owning/editing the existing listing (likely needs the submitter's login or an edit-request), not a fresh submission. Owed: a manual edit pass once ownership/edit access is confirmed. |
| punkpeye/awesome-mcp-servers | **PR #8098 CLOSED, not merged** (verified 2026-07-31) | Closed 2026-07 for inactivity: the reviewer bot requires a Glama quality-score badge in the PR before merge, and the Glama score was never obtained (see Glama row below — it's stuck at "not tested"). Do not reopen or file a new PR until the Glama listing is claimed and actually scored; the badge is a hard requirement, not optional. |
| Glama MCP | **Live and indexed, but unclaimed** (verified 2026-07-31 via live page load) | `https://glama.ai/mcp/servers/@Assay-Org/assay-truth-graph-mcp` is real and shows the "Official" tag, but: (1) description is stale (pre-2026-07-31 copy — Glama re-crawls asynchronously, no action needed for that specific gap, it should update on its own crawl cadence now that `glama.json` + README are pushed); (2) **quality score shows "not tested"** rather than any letter grade, most likely because Glama's automated crawler can't get past the OAuth wall to introspect tools — this is what's blocking the punkpeye PR above; (3) **license shows "F, not found"** — the repo has no LICENSE file, which is hurting the score and is likely required for several other directories too; (4) **listing is unclaimed** ("claim this server to access the admin panel") — claiming needs the founder's own GitHub-authenticated browser session, not something completable from this sandboxed session. **Two founder actions needed:** claim the listing at the URL above (GitHub sign-in), and decide a license for this repo (it's a thin manifest/config wrapper, not proprietary source — MIT or Apache-2.0 would be typical, but licensing is a real decision, not mine to make unilaterally). |
| mcp.so | Issue submitted (June) | https://github.com/chatmcp/mcpso/issues/2817 — not re-checked this session. |
| Smithery | Blocked on API key / account | `npx smithery@latest mcp publish ...` prompts for a Smithery API key from https://smithery.ai/account/api-keys. No `smithery` CLI installed locally as of 2026-07-31 either. Needs the founder to create/access a Smithery account. |
| Cline MCP Marketplace | Ready, not submitted | Issue template requires confirming Cline setup was tested from README/llms-install. Do this after a real Cline install test, then submit to https://github.com/cline/mcp-marketplace/issues/new/choose. |
| Cursor Directory | Blocked on sign-in — **confirmed live 2026-07-31** | Verified by loading https://cursor.directory directly: nav bar has a "Submit a plugin" button gated behind "Sign In" (GitHub OAuth), no PR-to-repo submission path found on the live site. ⚠ Correction: an earlier research pass in this project (2026-07-31 marketplace-submissions run) concluded this was a GitHub PR to `leerob/directories` — that was wrong / stale; do not act on it. The sign-in-gated flow above, matching this row's original June finding, is what's actually live. Needs the founder's own Cursor Directory account. |
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

## 2026-10-07 pass

| Store | Status |
|---|---|
| Official MCP Registry | v0.1.2 metadata pushed (icons fixed, MIT). **Publish pending founder device login** (`mcp-publisher login github`). Registry still serves v0.1.0. |
| PulseMCP | Listed (auto-ingested, "Official"): https://www.pulsemcp.com/servers/assay |
| Glama | Listed twice, unclaimed; needs founder claim + reviewer credentials. LICENSE now present. |
| punkpeye/awesome-remote-mcp-servers | PR https://github.com/punkpeye/awesome-remote-mcp-servers/pull/1293 (Marketing). The old awesome-mcp-servers list no longer takes remote-only servers. |
| Kilo Code Marketplace | PR https://github.com/Kilo-Org/kilo-marketplace/pull/333 |
| Docker MCP Catalog | PR https://github.com/docker/mcp-registry/pull/5490; test credentials form pending reviewer account |
| Claude Connectors + plugin directory | Portal is now https://claude.ai/directory/manage (any paid plan). Founder submission; see MANUAL-SUBMISSION-CHECKLIST.md. PRM `resource` fixed to the exact MCP URL (cki #1163). |
| OpenAI plugin directory (ChatGPT + Codex) | Founder submission; domain-challenge route ships in cki #1163. |
| Cursor Marketplace / cursor.directory | `.cursor-plugin/plugin.json` + LICENSE added; founder login to submit. |
| MCP.Directory, MCP Market, mcp.so | Free web forms, founder to submit (form submission from the agent was blocked). |
| Smithery | Founder account needed. |
