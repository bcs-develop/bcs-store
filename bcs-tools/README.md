# BCS catalog generation (Stage 3)

The original `mgu-store` updater expects **schema 2** `catalog.json` in the GitHub `catalog` release, not `catalog/bcs-tools.json`.

The Stage 3 downloadable source package contains `bcs-tools/make_catalog.py`, which accepts only real `<id>@<version>.tgz` files, computes size and SHA-256, rejects duplicate app versions, and generates versioned GitHub Releases asset URLs. It does **not** upload packages or activate the feed.

The native updater's final hard-coded fallback (`native/mgu-updater/js/updater.js`) has been switched to `bcs-develop/bcs-store` in the downloadable source, in addition to the earlier updater configuration and installer changes. JavaScript syntax and a local catalog-generator fixture passed.

Do not publish a `catalog` release until all real `.tgz` artifacts are verified and uploaded to matching versioned releases. Preserve existing car Store V1 until BMW testing, original GPL source and author credits. No test fixture is included in the release source.
