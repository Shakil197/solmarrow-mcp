# SolMarrow MCP

**Free AI agent social media posting.** Let Claude, ChatGPT, Cursor, LobeHub or any MCP client draft, schedule and publish posts to 19 social networks from one chat.

- **Free posting:** the free plan has unlimited posts and unlimited accounts. No card needed.
- **Multi-channel instantly:** X, LinkedIn, Facebook, Instagram, Threads, Bluesky, TikTok, YouTube, Pinterest, Mastodon, Telegram, Discord, Slack, Tumblr and more.
- **Safe by default:** agents save drafts or schedule at least 5 minutes ahead, so every post shows in your SolMarrow calendar first.

## Server

| | |
|---|---|
| URL | `https://mcp.solmarrow.com/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 (PKCE, dynamic client registration). No API key: you sign in to SolMarrow and click Allow. |

## Connect

**LobeHub:** Community → MCP → SolMarrow → Install, then sign in when asked.

**Claude / ChatGPT:** Settings → Connectors → add `https://mcp.solmarrow.com/mcp`.

**Claude Code:**

```bash
claude mcp add --transport http solmarrow https://mcp.solmarrow.com/mcp
```

**Cursor, VS Code and other `mcp.json` clients:**

```json
{
  "mcpServers": {
    "solmarrow": { "url": "https://mcp.solmarrow.com/mcp" }
  }
}
```

More clients: https://solmarrow.com/docs/ai-agents-mcp

## Tools

| Tool | What it does |
|---|---|
| `list_workspaces` | Your SolMarrow workspaces |
| `list_accounts` | Connected social accounts in a workspace |
| `create_post` | Save a draft or schedule a post (per-account text and options) |
| `list_posts` / `get_post` | Read posts and their status per network |
| `delete_post` | Delete a draft or scheduled post |
| `list_media` / `upload_media_from_url` / `create_media_upload` / `finish_media_upload` | Media library and uploads |
| `get_analytics` | Likes, comments, shares and views |

## Try it

> "List my SolMarrow accounts, then schedule a LinkedIn and X post for tomorrow 9:00 announcing our new feature."

## Links

- Website: https://solmarrow.com
- Docs: https://solmarrow.com/docs
- Privacy: https://solmarrow.com/privacy · Terms: https://solmarrow.com/terms
- Support: support@solmarrow.com

This repository holds the listing for the hosted SolMarrow MCP server; the server itself is run by SolMarrow.
