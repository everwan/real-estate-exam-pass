# Remote Content Artifacts

This directory is the publish target for encrypted remote content bundles used by:

- `https://github.com/everwan/real-estate-exam-pass`

Current state:

- stale DMV-era encrypted bundles were removed
- `manifest.json` is intentionally empty until new bundles are generated

To generate fresh bundles for this project:

1. set `CONTENT_PASSWORD`
2. optionally set `CONTENT_BASE_URL`
3. run `npm run content:remote` from `apps/mobile`
4. optionally run `npm run content:verify`

Generated manifests include a `sourceHash` for each bundle. The app uses that hash to detect real content changes, so a remote question-bank update is picked up even when the previous app install already has a content bundle recorded.

Recommended base URL:

- `https://raw.githubusercontent.com/everwan/real-estate-exam-pass/main/appdata`
