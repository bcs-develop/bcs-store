# BCS Store v2.0.1 OTA test candidate

This branch is a staging branch, **not a published OTA release**.

## Candidate
- App ID: `bcs_store`
- Version: `2.0.1`
- Package: `bcs_store@2.0.1.tgz`
- SHA-256: `ad053c9ff30dd8293eda73725215cd329e48e43c477977022493ec51752686bd`
- Source: BCS MGU v5 GitHub Manage Sources test installer uploaded on 2026-11-07.
- Changes: compact/minimal interface refinement; preserves Store, Installed, Settings, sources and updater actions.
- The upstream Robert updater packages are unchanged.

## Important packaging issue corrected
The uploaded v2.0.0 installable tarball contained **truncated** `src/store.js`, `src/store_ui.js`, and `src/store_compact.js`. The candidate restores the complete versions from the ZIP's included source before packaging. Test carefully on the bench.

## Required before OTA is enabled
1. Upload the **exact** matching `bcs_store@2.0.1.tgz` and `catalog.json` from the candidate ZIP to a location readable by mgu-updater. Do not rebuild after calculating the checksum.
2. Confirm the updater's expected source/catalog format and GitHub release discovery behavior.
3. Confirm v2.0.0 can discover the candidate through the BCS Store UI.
4. On a backed-up ID7 bench unit, confirm download, integrity validation, install, restart and rollback.
5. Publish a production GitHub Release only after passing those checks.

A regular GitHub source ZIP or branch commit alone is **not** a compatible OTA release. No live release is asserted here.
