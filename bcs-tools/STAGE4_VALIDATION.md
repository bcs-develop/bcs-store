# Stage 4 catalog validation

Local source package: `BCS_STORE_V2_OPTION_A_STAGE4_VALIDATED_CATALOG_SOURCE.zip` (not published as a GitHub release).

- Tightened package filenames to match original updater's three-component semantic version parser (`x.y.z`).
- Rejects invalid `.tgz` archives, archives without root `manifest.json`, unsafe traversal paths and tar links.
- Includes `bcs-tools/test_catalog.py` with four unit tests (valid package, corrupt package, missing manifest, unsupported prerelease version).
- Validated generated schema-2 `catalog.json` against original `native/mgu-updater/js/catalog.js` Node parser.
- No live catalog, actual GitHub release assets, vehicle deployment, or BCS Luxury UI build in this stage.

**Important:** Do not activate a GitHub catalog until all release assets are uploaded and tested. Existing BCS Store V1 remains unchanged.
