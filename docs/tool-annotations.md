# ChatGPT / Claude remote MCP tool annotations

Source of truth: `apps/daemon/src/mcp/mcp.ts` (`REMOTE_MCP_TOOL_NAMES` + `MCP_TOOL_DEFS`).

| Tool | readOnlyHint | destructiveHint | openWorldHint |
| ---- | -----------: | --------------: | ------------: |
| `list_projects` | yes | **no (explicit)** | no |
| `get_project` | yes | **no (explicit)** | no |
| `get_file` | yes | **no (explicit)** | no |
| `list_files` | yes | **no (explicit)** | no |
| `search_files` | yes | **no (explicit)** | no |
| `list_connectors` | yes | **no (explicit)** | no |
| `get_plan` | yes | **no (explicit)** | no |
| `get_plan_information` | yes | **no (explicit)** | no |
| `create_project` | no | no | no |
| `write_file` | no | yes | no |
| `apply_code` | no | yes | no |
| `flutter_preview` | no | no | no |
| `build_android` | no | no | yes |
| `flutter_github` | no | no | yes |
| `flutter_deploy` | no | no* | yes |
| `flutter_figma` | no | no | yes |
| `connect_connector` | no | no | yes |
| `delete_file` | no | yes* | no |
| `delete_project` | no | yes* | no |

\* `flutter_deploy` action=`start`, `delete_file`, and `delete_project` require `confirm: true`.

OpenAI’s ChatGPT Apps form requires **every** tool to publish `destructiveHint` explicitly — including read-only tools (`false`). See `tool-justifications.md` and `chatgpt-app-submission.json`.

## Intentionally absent on remote ChatGPT surface

- `flutter_apk` (duplicate of `build_android`)
- `upgrade_plan` (renamed to `get_plan_information`)
- `list_plugins` (unbounded catalogue; local stdio only until a paginated Flutter-scoped version ships)
- `start_run` / `get_run` / `cancel_run` / `list_agents` / `get_active_context` (local stdio / studio)
