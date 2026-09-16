# Marketplace test cases

Use a fully featured demo account (see `demo-account.md`). Record run ids / screenshots for the review form.

## Positive (5)

### P1 — Create project
1. Call `create_project` with a unique name.
2. Expect project `id` + `name`.
3. Call `list_projects` and confirm the project appears with only public fields.

### P2 — Apply code + preview
1. `apply_code` with a minimal Flutter `lib/main.dart` (and package-correct imports).
2. `flutter_preview` action=`start`, then poll `status` until `running` or `failed`.
3. On success, open `url` in a browser.

### P3 — Build Android APK
1. On a plan that allows APK builds, call `build_android` action=`start`.
2. Poll `status` until `success`.
3. Open `downloadUrl`.

### P4 — GitHub connect
1. `flutter_github` action=`connect`.
2. Open returned install/authorize URL, complete OAuth.
3. `flutter_github` action=`status` shows linked state (or clear next step).

### P5 — Figma connect / extract (if demo file provided)
1. `connect_connector` connector=`figma` if needed; complete OAuth.
2. `create_project` with `figmaUrl` or `flutter_figma` action=`extract`.
3. Poll until extract ready; read `figma/OVERVIEW.md` via `get_file`.

## Negative (3)

### N1 — Locked plan feature
1. On Free (or a plan without APK), call `build_android`.
2. Expect `locked: true`, `code: FEATURE_LOCKED`, `pricingInfoUrl` pointing at `/pricing/`.
3. Confirm no Polar/checkout URL and no credit charge for the lock.

### N2 — Destructive without confirm
1. Call `delete_project` without `confirm: true` (or with `confirm: false`).
2. Expect an error; project still listed.

### N3 — Unsupported connector / missing project
1. `connect_connector` with connector=`slack` (or another non-allowlisted id) → error naming allowed connectors.
2. Or call `apply_code` without `project` on ChatGPT MCP → error that project is required.
