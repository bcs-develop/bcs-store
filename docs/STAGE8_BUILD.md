# Stage 8: donor-linked compiled candidate

`node apps/robertn_store/tools/build.js --sdk BCS_STORE_V1_WORKING.tgz` succeeded. Outputs: `robertn_store@0.9.15.src.tgz` (source package), `robertn_store@0.9.15.tgz` (compiled candidate). Donor is the user's working BCS Store V1 package. `node tools/test_screens.js`: 36 screen configurations / 896 checks pass. `node tools/test_store.js`: 302 checks pass. Syntax check passed.

**Not installable/released**: compiled candidate still has `robertn_store@0.9.15` identity, not installed BCS `bcs_store@1.0.1`; official logo not integrated; no BMW test; no live BCS GitHub catalog. Preserve existing V1. The complete Stage 8 source and candidate are in the separately downloadable ZIP, not yet committed wholesale to this branch. GPL and upstream attribution retained.
