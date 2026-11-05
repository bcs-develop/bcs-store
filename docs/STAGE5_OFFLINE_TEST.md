# Stage 5: real V1 donor package offline test

A real `bcs_store@1.0.1.tgz` archive (the user's working V1 donor, 3.5 MB) was used **locally** to generate a schema-2 catalog with SHA-256 and byte size. The original `native/mgu-updater/js/catalog.js` parser accepted it. The updater's `plan()` returned `update` for installed 1.0.0 against catalog 1.0.1, and `installed` for 1.0.1. Four Python catalog validation tests passed.

The downloadable Stage 5 ZIP includes original source, the actual donor archive and generated catalog for **offline validation only**. No compiled donor archive or live release was uploaded to GitHub. The catalog's planned GitHub release URL is not live. Before publishing, verify redistribution rights and GPL source availability; do not publish SSH keys or customer data. No BMW installation/update test has occurred.
