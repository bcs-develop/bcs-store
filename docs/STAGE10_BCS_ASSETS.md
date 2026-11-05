# Stage 10 — Original BCS assets restored

The compiled candidate `bcs_store@1.0.2.tgz` has been repacked using the three exact image assets from the user-provided working BCS Store V1 archive:

- `rhmiData/variantGroups/Common/images/store_icon.png` (140x140)
- `rhmiData/variantGroups/Common/images/bcs_logo.png` (2048x432)
- `rhmiData/variantGroups/Common/images/bcs_store_icon_full.png` (1254x1254)

The three assets were verified byte-for-byte against the working donor. Candidate package SHA-256: `aa7de635fa13531c641ebdfd2eb1d47737a43dbd4d5cc0779354ca23bfe05b70`.

This is **not** a completed RHMI integration or a verified installable build. The assets are present in the package, but BMW screen rendering, runtime compatibility, app identity migration, and GitHub update delivery remain untested. Do not overwrite V1. Full source and candidate are supplied in a separate ZIP, not published to GitHub Releases.
