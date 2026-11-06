# BCS Store v2 — Dual GitHub Release Channels (bench-test candidate)

BCS Store owns its GitHub source configuration, not the Windows installer.

- `bcs_store` updates, UI and control logic: `bcs-develop/bcs-store:releases`
- Future BCS apps: `bcs-develop/bcs-mgu-apps:releases`
- Upstream tool updates remain on Robert Nisipeanu's original GitHub source. Do not fork, replace, or pin upstream tools to BCS.
- The Store's existing updater socket protocol already provides `check`, `install`, `source-add`, and `source-remove`. Store v2 test build checks for missing BCS sources and requests `source-add` through the existing privileged updater API.
- The Store's UI, source-management screens, update actions and source registration code live in the `bcs_store` app package. Updating only `mgu-updater` must not overwrite them.
- The Store app source must be published as complete corresponding GPL-covered source with Robert's original credits and license notices. Keep commercial Windows installer code, customer data, and SSH/signing keys private.
- Never publish an untested `bcs_store@2.0.0.tgz` as a customer update. The current v2 package is a versioned/branded v1.0.1-derived test build, not the separate v2 codebase mentioned previously.

## GitHub publishing requirements

1. Publish corresponding Store source and build instructions to this repository.
2. Publish a verified `bcs_store@<version>.tgz` as a GitHub Release asset, with updater-compatible catalog or release metadata.
3. Publish BCS-owned future apps to `bcs-mgu-apps` as separate releases, not in this Store repository.
4. Test both source registrations, update detection, update installation, rollback, and upstream Robert tool upgrades on a backed-up bench head unit.
5. Promote only after checks pass.

**Current status:** configuration is in a local v5 installer test ZIP; no live Store release has been published. The two GitHub sources are not guaranteed to be active until on-car tests confirm updater authorization and connectivity.
