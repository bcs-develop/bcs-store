# BCS Store V2: upstream catalog migration

Original source archive inspected: `mgu-store-main(3).zip`.

## Actual upstream mechanism

- `deploy/sources.json` seeds `mgu-updater` sources; currently includes `robertnisipeanu/mgu-store` as `builtin`, plus `cauliflowermossgrape/idrive7-apps`, `robertnisipeanu/idrive-apps`, and `IterioDev/car-apps`.
- `native/mgu-updater` also has a hard-coded `builtin_repo` fallback to `robertnisipeanu/mgu-store`. Editing `deploy/sources.json` **alone** is insufficient.
- Updater reads `/var/opt/mgu-updater/sources.json` on a vehicle; installer seeding does not automatically replace existing vehicle configuration.
- Upstream publishing expects a GitHub release named/tagged `catalog` with asset `catalog.json`, plus versioned package release assets named `<id>@<version>.tgz`. Existing `catalog/bcs-tools.json` is **not** this format.
- `apps/robertn_store` is the editable app source, with `tools/build.js` and a source-package workflow; preserve its OAP runner and SDK build process.

## Safe implementation steps

1. Preserve original `mgu-store` source and copyright/GPL/third-party notices. Create BCS fork with UI modifications and BCS branding; keep Robert attribution.
2. Add BCS repository as the desired default source **both** in installer seeds and updater built-in fallback, with tests updated. Retain upstream optional sources only when licensed/approved and explicitly desired.
3. Produce a valid `catalog.json` and GitHub Releases assets with SHA-256 and sizes; do not publish placeholders as active feeds.
4. Verify source and update behavior in an isolated test and on a backed-up bench unit. Migrate existing vehicle sources only after verification, with a reversible backup of `/var/opt/mgu-updater/sources.json`.
5. Never silently overwrite users' existing configured sources, credentials or installed app provenance.

**Current status:** planning and inspection only. No BMW or GitHub release feed changed. Do not install a package based on this document.
