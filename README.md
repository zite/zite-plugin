# Zite plugin

Build apps on your [Zite](https://www.zite.com) databases from Cursor and Grok Build,
through the hosted Zite MCP server.

## What it does

Connects your agent to `https://mcp.zite.com/mcp`, which exposes tools for:

- **Databases** — list workspaces, inspect schemas, query/create/update/delete records, run SQL
- **Tables and fields** — create, update and delete
- **Apps** — scaffold, edit, typecheck, build, commit and publish

Database tools are available on every plan, including free. The app-builder tools are on
the Business plan and above; the first `create_sandbox` call starts a free 7-day trial with
no card required. Apps can also be built in the Zite editor on any plan.

## Install

Marketplace listings for Cursor and Grok Build are in review. Until they are live,
add the server directly.

**Cursor** — add to `.cursor/mcp.json`:

```json
{ "mcpServers": { "zite": { "url": "https://mcp.zite.com/mcp" } } }
```

**Any MCP client** — point it at `https://mcp.zite.com/mcp` over streamable HTTP and
complete the OAuth sign-in when prompted.

## Authentication

Sign-in is OAuth 2.1. The server returns `401` with RFC 9728 protected-resource metadata
pointing at `https://server.zite.com`, which supports dynamic client registration and PKCE,
so no credentials need to be issued in advance — your client completes the flow on first use.

## Network endpoints

This plugin ships no executable code. It declares one remote MCP server:

| Endpoint | Purpose |
|---|---|
| `https://mcp.zite.com/mcp` | Zite MCP server (streamable HTTP) |
| `https://server.zite.com` | OAuth authorization server |

## Links

- [Documentation](https://developers.zite.com/)
- [Support](mailto:support@zite.com)

## License

MIT — see [LICENSE](LICENSE).
