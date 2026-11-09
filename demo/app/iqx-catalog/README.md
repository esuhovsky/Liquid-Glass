# AI4-IQX — Liquid Glass Interactive Component Showroom
**As of:** 2026-11-09 | **Status:** DEV/TEST, saved from live GCP container source; not deployed to production.

## Open locally
Launch the repository's Next.js demo with Node dependencies installed (`npm ci && npm run site -- --hostname 0.0.0.0`), then navigate to `/iqx-catalog`. This route uses the **actual** `@zakisheriff/liquid-glass` React package and stylesheet provided by the upstream demo setup. It is not a standalone HTML file.

## Existing GCP testing instance
- Source checkout: `/home/adminmain_ai4agencies_ai/iqx-liquid-glass-test`
- Docker container name: `iqx-liquid-glass-test`
- Host-only address: `http://127.0.0.1:3187/iqx-catalog` (accessible **on the GCP VM**, not directly bookmarkable from a user's laptop)
- Container command uses `node:22-bookworm-slim`, mounts the source checkout, runs `npm ci` and `npm run site -- --hostname 0.0.0.0`. Existing container is maintained independently of GitHub.
- To restart existing stopped container: `docker start iqx-liquid-glass-test`. To stop while retaining it: `docker stop iqx-liquid-glass-test`.
- Last witnessed status when saved: Docker Up; HTTP GET 200 from local URL. No authenticated HTTPS public ingress yet.

## Current interactive controls
Nine left-menu components: Button, Switch, Slider, Segmented, Navigation, Menu, Input, Card, Sheet. The right-hand area displays live component state and common controls: intensity, accent color and theme; size/variant, toggle disable, slider value/step/block, compact mode, label visibility, menu actions, text entry, card radius/clear mode, and sheet detents. Original demo `/studio` and `/docs` linked below the controls.

## Not yet implemented
- Copy Configuration button.
- Save Configuration / Save as Template and GitHub write-back.
- My Templates, reload, revisions, duplicate detection, approval status.
- Complete coverage of **every** documented prop/variant. This page covers representative controls; API completeness needs separate acceptance tests.
- Authenticated public HTTPS URL.
- Integration into approved IQX main GUI.

## Source-of-truth and safety
This copy is version-controlled as a development preview; do not confuse it with the v7/v8 IQX landing-page preview, a production system, or an approved final catalog. Do not expose GitHub credentials in browser code. Before adding Save/Load and new components, check schema, version/lock, duplicate detection, and owner gate documented in the IQX Master Skills draft PR #228. Do not automatically sync or overwrite master GUI.
