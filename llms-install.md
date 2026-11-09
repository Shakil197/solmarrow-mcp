# SolMarrow MCP: install guide for AI agents

SolMarrow is a remote MCP server. There is nothing to clone, build or install locally, and no API key is needed.

## Steps

1. Add this remote server to your MCP client config:
   - URL: `https://mcp.solmarrow.com/mcp`
   - Transport: Streamable HTTP
2. On first use the client opens a browser. The user signs in to SolMarrow (a free account works) and clicks Allow. This is OAuth 2.1 with PKCE and dynamic client registration, so no secret is stored in the config.
3. Call `list_workspaces`, then `list_accounts` to see the connected social accounts.

## Config examples

Claude Code:

```bash
claude mcp add --transport http solmarrow https://mcp.solmarrow.com/mcp
```

Cline, Cursor, VS Code and other `mcp.json` clients:

```json
{
  "mcpServers": {
    "solmarrow": {
      "url": "https://mcp.solmarrow.com/mcp",
      "type": "streamableHttp"
    }
  }
}
```

## Safety behaviour

- `create_post` only saves a draft or schedules at least 5 minutes ahead. Nothing is published instantly.
- The server cannot connect or disconnect social accounts. The user does that at https://app.solmarrow.com.
- Limit: 300 agent posts per person per day.

## Troubleshooting

- Sign-in page does not open: the client must support remote MCP with OAuth. Update the client.
- "No accounts": the user must connect at least one social account in SolMarrow first.
- Support: support@solmarrow.com
