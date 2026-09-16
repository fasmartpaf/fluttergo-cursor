# FlutterGo MCP listing copy

## Short description

Create, preview, build, export and deploy Flutter applications directly from your AI assistant.

## Long description

FlutterGo.AI connects your AI assistant to a cloud Flutter studio. Authenticate with your FlutterGo account, then create projects, write Dart and assets, run a cloud web preview, build downloadable Android APKs, sync with GitHub, import Figma, and prepare store deploys — without shipping Apple or Play secrets through the chat.

One production MCP server powers ChatGPT, Claude, Cursor, and other MCP clients:

`https://fluttergo.ai/api/mcp/remote`

Plan information tools never open checkout inside the assistant. If a feature is unavailable, FlutterGo explains that and links to https://fluttergo.ai/pricing/ for information only.

## Category

Developer tools / App builders / Flutter

## Publisher

FLUTTERGO.AI (PRIVATE) LIMITED  
Support: support@fluttergo.ai  
Privacy: https://fluttergo.ai/privacy/  
Terms: https://fluttergo.ai/terms/  
Security: https://fluttergo.ai/security/  
MCP docs: https://fluttergo.ai/integrations/mcp/

## Release notes (initial marketplace submission)

- Production remote MCP with OAuth (PKCE)
- Cloud Flutter preview and Android APK builds
- GitHub, Figma, Firebase, and Supabase connectors (ChatGPT surface)
- Plan and permission tools without price catalogs or in-chat checkout
- Confirmation required for file deletion, project deletion, and store deploy start
- Sanitized project listings (no internal owner ids or filesystem paths)
- GitHub status responses omit internal installation ids
- Plugin catalogue omitted from the ChatGPT remote surface (local stdio only)

## Suggested starter prompts

1. Create a Flutter cafe ordering app with local icons and a cloud preview.
2. Apply these Dart files to my FlutterGo project and fix analyze errors until preview runs.
3. Build an Android APK for this project and give me the download link.
4. Connect GitHub and push this FlutterGo project to a new private repo.
5. Import this Figma file into my FlutterGo project and implement the screens.
