# OAuth instructions (reviewers)

## Endpoint

- MCP: `https://fluttergo.ai/api/mcp/remote`
- OAuth discovery: `https://fluttergo.ai/api/mcp/remote/.well-known/oauth-authorization-server`
- Protected resource metadata: `https://fluttergo.ai/api/mcp/remote/.well-known/oauth-protected-resource`
- RFC 9728 path-aware alias: `https://fluttergo.ai/.well-known/oauth-protected-resource/api/mcp/remote`

Discovery responses are cacheable (`Cache-Control: public, max-age=300`). Both protected-resource URLs must return HTTP 200 JSON quickly.

## Flow

1. Client registers (dynamic client registration) or uses a pre-registered redirect URI.
2. Authorization request uses PKCE (`code_challenge` / `S256`).
3. User signs in at FlutterGo and clicks Allow.
4. Client exchanges the code at the token endpoint for an access token.
5. `Authorization: Bearer <token>` on `tools/list` and `tools/call`.

## Reviewer checklist

- [ ] Login with the provided demo account
- [ ] Allow the client
- [ ] `tools/list` returns the remote tool set (includes `build_android`, not `flutter_apk`)
- [ ] Token refresh works after expiry (or force refresh if the client supports it)
- [ ] Revoking / signing out prevents further tool calls

## Security notes for reviewers

- Do not paste Apple/Play certificate material into chat or tool args.
- `get_plan` must not return subscription price tables or credit-pack SKUs.
- `get_plan_information` only returns an informational pricing URL.
