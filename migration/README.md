# BCS Store V2 migration configuration

This is **development-only** configuration, not an active catalog or installable release.

The `deploy/sources.json` file sets the BCS GitHub repository as the built-in source. The original updater also requires `native/mgu-updater/updater.conf` to set `builtin_repo = bcs-develop/bcs-store` and `deploy/mgu-install.js` to use `const STORE_REPO = 'bcs-develop/bcs-store';`. `release/publish.js` should default to `github:bcs-develop/bcs-store`.

The actual source ZIP has been provided by the user. The original build pipeline, license notices and attribution must be retained. Existing vehicle `/var/opt/mgu-updater/sources.json` is not overwritten by first-install seeding.

Do not activate until a valid `catalog` release with `catalog.json` and verified versioned `.tgz` release assets is published.
