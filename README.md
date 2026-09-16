# FlutterGo Plugin for Cursor

Create, edit, preview, and build Flutter applications from Cursor through [FlutterGo.AI](https://fluttergo.ai)’s hosted MCP server.

**MCP endpoint (production):**

```text
https://fluttergo.ai/api/mcp/remote
```

**Official MCP Registry:** `ai.fluttergo/remote`  
**Publisher:** FLUTTERGO.AI (PRIVATE) LIMITED · support@fluttergo.ai  
**This public repo:** https://github.com/fasmartpaf/fluttergo-cursor

This plugin ships **no install scripts, no credentials, and no local binaries**. It only declares a remote Streamable HTTP MCP URL. On first tool use, Cursor opens FlutterGo’s OAuth (PKCE) sign-in in the browser.

## Why this package exists

Cursor’s directory security scan correctly notes that remote OAuth MCP trust rests with the operator. This **public** repository gives reviewers:

- An auditable Git tree (manifest + `mcp.json` only — no private app source)
- A clean package (no secrets, no prompt injection, no install hooks)
- OAuth / test / listing docs under [`docs/`](./docs/)

The live tool surface is the same production MCP used for ChatGPT / Claude / other MCP clients — not a Cursor-only fork.

## Install (local / manual)

1. Open **Cursor Settings → MCP** (or install from the directory once listed).
2. Add server URL `https://fluttergo.ai/api/mcp/remote`, or install this plugin from this repo.
3. On first MCP use, approve FlutterGo OAuth in the browser.

## What it does

| Capability | Example tools |
| --- | --- |
| Projects | `list_projects`, `get_project`, `create_project`, `delete_project` |
| Files | `list_files`, `get_file`, `search_files`, `write_file`, `apply_code`, `delete_file` |
| Preview & build | `flutter_preview`, `build_android` |
| Connectors | `list_connectors`, `connect_connector`, `flutter_github`, `flutter_deploy`, `flutter_figma` |
| Plan | `get_plan`, `get_plan_information` |

Remote MCP work uses the signed-in FlutterGo account’s plan and credits (same as the FlutterGo studio).

## Security & trust (for reviewers)

| Topic | Detail |
| --- | --- |
| Transport | HTTPS Streamable HTTP MCP |
| Auth | OAuth 2.1 + PKCE (no long-lived API key in the plugin) |
| Scope | Authenticated user’s FlutterGo projects and allowlisted connectors |
| Secrets | Apple / Play certificate material is never requested in chat |
| Destructive tools | Confirm before file/project delete and store deploy start |
| Pricing | Plan tools do not open checkout; informational link only |

### Public policy pages

- Privacy: https://fluttergo.ai/privacy/
- Terms: https://fluttergo.ai/terms/
- Security: https://fluttergo.ai/security/
- Support: https://fluttergo.ai/support/
- MCP docs: https://fluttergo.ai/integrations/mcp/

### Reviewer docs (this repo)

- OAuth steps: [`docs/oauth.md`](./docs/oauth.md)
- Test cases: [`docs/test-cases.md`](./docs/test-cases.md)
- Tool annotations: [`docs/tool-annotations.md`](./docs/tool-annotations.md)
- Listing copy: [`docs/listing.md`](./docs/listing.md)
- Registry metadata: [`docs/server.json`](./docs/server.json)

Demo account credentials are **not** committed. Request them privately from support@fluttergo.ai for review.

## Network endpoints

| URL | Purpose |
| --- | --- |
| `https://fluttergo.ai/api/mcp/remote` | Hosted MCP |
| `https://fluttergo.ai/api/mcp/remote/.well-known/oauth-authorization-server` | OAuth discovery |
| `https://fluttergo.ai/api/mcp/remote/.well-known/oauth-protected-resource` | Protected resource metadata |

## Example prompts

```text
Create a Flutter cafe ordering app in FlutterGo and show me the project id.
```

```text
In my FlutterGo project, apply a Material 3 dark theme to lib/main.dart and open a preview.
```

```text
Build an Android APK for my FlutterGo project and give me the download URL when it finishes.
```

## Resubmit to Cursor directory

See [`SUBMIT.md`](./SUBMIT.md).

## License

Apache-2.0
