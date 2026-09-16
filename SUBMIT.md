# Cursor directory form — paste values

Repo: https://github.com/fasmartpaf/fluttergo-cursor (public)

## Fields

| Field | Value |
| --- | --- |
| Type | MCP Server |
| Name | `fluttergo` |
| Description | Create, preview, build, and deploy Flutter apps via FlutterGo.AI cloud MCP (OAuth). |
| Repository | `https://github.com/fasmartpaf/fluttergo-cursor` |

## Content (paste exactly)

```json
{
  "mcpServers": {
    "fluttergo": {
      "url": "https://fluttergo.ai/api/mcp/remote"
    }
  }
}
```

## After submit

Email `marketplace-publishing@cursor.com`:

Subject: Manual review — FlutterGo remote MCP (`ai.fluttergo/remote`)

Body:

```text
Hi,

Please manually review the FlutterGo Cursor plugin after the automated
remote-OAuth medium-severity hold.

- Plugin name: fluttergo
- Public repo: https://github.com/fasmartpaf/fluttergo-cursor
- MCP URL: https://fluttergo.ai/api/mcp/remote
- Official MCP Registry: ai.fluttergo/remote
- Auth: OAuth 2.1 + PKCE (no API key in the plugin)
- Docs: privacy / terms / security / integrations/mcp on fluttergo.ai
- Reviewer OAuth + tests: https://github.com/fasmartpaf/fluttergo-cursor/tree/main/docs

Happy to provide a demo account privately.

Thanks,
FlutterGo.AI
```
