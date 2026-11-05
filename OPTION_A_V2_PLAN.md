# BCS Store V2 — Option A (original-store reskin)

Status: development branch only. **Not an installable release or active feed.**

## Foundation
- Preserve the original Robert Store / working BCS Store V1 application architecture, OAP runner, SDK integration, app identity, installation/removal backend, Wi-Fi and existing network behavior.
- Make UI and selected feature changes against the **corresponding editable upstream source** and its original build pipeline, not by treating the compiled V1 TGZ as source.
- Preserve Robert Nisipeanu (IterioDev) attribution, original copyright and GPL license notices, and publish complete corresponding modified source.

## Approved V2 UI scope
- BCS Luxury dark styling, BCS icon, and consistent dialogs.
- Apps, Installed, Tools, Settings and Wi-Fi Settings, with 4 app cards per row where the ID7/ID8 layout supports it.
- Preserve original Store install/update/delete, Wi-Fi and networking behavior; changes must be tested individually.
- Keep source/account internals hidden from ordinary user UI only when doing so does not break updates or GPL source availability.

## GitHub integration
- Repository: https://github.com/bcs-develop/bcs-store
- Development branch: develop/option-a-v2-reskin
- Intended stable catalog base: https://raw.githubusercontent.com/bcs-develop/bcs-store/main/catalog/
- GitHub Releases will host versioned built packages with SHA-256 hashes; only publish the catalog after a verified release.
- The Store must be explicitly configured to consume a tested BCS catalog; **creating this document does not change the app's source URLs or enable updates**.

## Release gates
1. Audit original editable Store source and original build process; compare against the working V1 TGZ.
2. Implement a minimal reskin and rebuild using original pipeline.
3. Validate Node.js 8, ID7/ID8 manifests, package hashes and SDK initialization.
4. Confirm source URLs and catalog format against the original updater; avoid changing backend behavior without necessity.
5. Back up working V1 and test install, UI, Wi-Fi, app download/install/remove, updates and rollback on a bench BMW.
6. Publish complete GPL-covered source, applicable third-party notices, signed-off release artifacts, hashes and tested catalog.

No private keys, VIN/customer data, licensing tokens or secrets may be committed.
