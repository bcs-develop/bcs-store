# BCS Store OTA integration — Installer v5.0

**Status: staging / not published.** This repository does not yet contain a verified BCS Store GitHub Release. Do not advertise OTA functionality to customers until the checks below pass.

## Feed configuration

- GitHub repository: `bcs-develop/bcs-store`
- Updater source type: `github`
- Channel: `releases`
- Additional source: `bcs-develop/bcs-store:releases`
- Store application ID: `bcs_store`
- Installer version: `5.0`
- Current bundled Store version in v5 installer: `1.0.1` (**not** v5)

In the v5 Windows installer, the **Enable GitHub Updates** button adds this source through the updater's persistent local configuration and restarts only the updater service. The existing Robert upstream source remains available for its runtime dependencies. Existing app sources must not be deleted or replaced.

## Required OTA publication format

1. Build and version the GPL-covered `bcs_store` source; retain Robert Nisipeanu/IterioDev credits, corresponding source, license notices and notices for bundled components.
2. Publish a GitHub Release containing `catalog.json` as a release asset and the exact `bcs_store@x.y.z.tgz` asset referenced by the catalog.
3. Use the mgu-updater **schema 2** catalog format, with `components[]` entries including `id`, `kind`, `version`, and `artifact` containing `name`, `size`, `sha256`, and valid URL (or an asset name resolved by the release-source reader).
4. Ensure semantic version increases; never replace a published version with different package bytes.
5. Confirm the head unit downloads and verifies SHA-256 before installation, then offers the user a deliberate update choice and supported rollback.
6. Verify compatibility and source ownership rules for existing `bcs_store` installations.
7. Ensure Store source releases **exclude** private commercial installer code, customer data, activation tokens, signing secrets, SSH private keys, firmware/flash material, and unlicensed third-party dependencies.

## Safe rollout

- [ ] Include complete corresponding modified GPL Store source and original notices.
- [ ] Audit redistribution licenses for native dependencies and packaged assets.
- [ ] Build test Store source artifact using the reproducible upstream release tooling.
- [ ] Test ID7 and ID8 installation and launch on backed-up, stable-power bench units.
- [ ] Test live version detection on the `releases` channel.
- [ ] Test SHA-256/size verification and corrupted download refusal.
- [ ] Test user approval, interrupted download, install interruption, updater restart, Delete, Undo, and rollback.
- [ ] Validate Store update while app is running; ensure no unwanted reboot.
- [ ] Publish approved release assets and catalog only **after** all tests pass.

## Important distinctions

The existing `catalog/bcs-tools.json` is a BCS planning metadata file, **not** the `catalog.json` GitHub release asset consumed by the MGU updater. No OTA update is live merely because this document or the v5 installer exists.

The ZIP containing the Windows installer and head-unit unlock resources is a **private distribution build** and must not be pushed directly to this public repository.
