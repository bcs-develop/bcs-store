# BCS Source Guard — Installer v5

The installer protects two GitHub release sources:
- **BCS Store**: bcs-develop/bcs-store:releases (app ID: bcs_store)
- **BCS future MGU apps**: bcs-develop/bcs-mgu-apps:releases

The v5 installer has **Check BCS GitHub Sources** (read-only) and **Repair / Protect BCS Sources**. Repair checks both /var/opt/mgu-updater/updater.local.conf and /var/opt/mgu-updater/sources.json, preserves third-party sources, backs up the originals, and stores a separate on-car helper under /var/opt/bcs-source-guard/. Never store the guard only in mgu-updater/current/, since that folder is overwritten during tool updates.

**Important:** default_sources alone cannot restore a repo that was registered and later deleted: the updater remembers one-time source registration. The guard checks and can restore both stored source entries. This v5 implementation is **manual** (no background service or automatic updater restart). Run after tool upgrades or when sources disappear, during a safe maintenance window.

No OTA feed is live until valid and licensed release packages plus an updater-compatible catalog are published and tested on backed-up BMW MGU hardware. Keep private installer content, SSH keys, activation secrets, firmware resources, and customer information out of these public repositories. Preserve all applicable upstream copyright and GPL notices.
