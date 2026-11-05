# BCS Store release checklist

- [ ] Review GPL obligations and include upstream LICENSE, copyright notices and complete corresponding modified Store source.
- [ ] Review redistribution licenses for app-privacy, mgu-deploy, mgu-python, mgu-render, mgu-updater, mgu-uplink and other bundled apps.
- [ ] Confirm no private SSH keys, license tokens/signing secrets or customer data are included.
- [ ] Rebuild bcs_store with the BCS catalog endpoint and retain Robert's attribution.
- [ ] Upload versioned artifacts as GitHub Release assets and publish a catalog with HTTPS download URLs and SHA-256 hashes.
- [ ] Test install, update, rollback and cache cleanup on a backed-up bench MGU.
- [ ] Verify existing units migrate away from old upstream source settings only after a successful BCS feed test.
