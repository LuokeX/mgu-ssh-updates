# MGU-SSH updates

Signed update artifacts for the MGU-SSH Windows client.

## 1.0.9 safety-check preview

Release `v1.0.9` is a **prerelease**. It includes the confirmed projection-file
permission fix and installation safety checks, but has not completed a full
head-unit emulator or real-vehicle cold-boot acceptance test. It is not a
promise that every vehicle will be free of restart loops. Updating the PC
software alone does not repair files already installed on a head unit.

- `latest.json` / `latest.json.sig`: the Ed25519-signed update manifest.
- Releases: versioned full and update Windows packages, SHA-256 sidecars and
  a validation record. Both packages include all 8 fixed `data/assets` input
  files and have identical contained file bytes.
- The fixed SSH/debug assets include upstream static key/certificate material;
  they are not personal vehicle enrollment keys or the update-signing key.
- The client verifies the manifest signature and package SHA-256.
- 1.0.9 is an optional update: `minimum` remains 1.0.5. It does not raise the
  mandatory-update floor.

The desktop installer wrapper is locally maintained. The bundled official
cluster-render 0.4.0, waze-on-cluster 0.9.0 and robertn_waze_cluster 0.6.0
release artifacts are unchanged. A component version rollback alone does not
resolve the confirmed restrictive-umask permission defect in older patchers.

Source projects and licenses:

- idrive7-8-ssh-root: https://github.com/cauliflowermossgrape/idrive7-8-ssh-root
- idrive-apps: https://github.com/robertnisipeanu/idrive-apps
- mgu-store: https://github.com/robertnisipeanu/mgu-store

GPL-3.0-or-later / MPL-2.0 and third-party notices are included in the package.
The desktop wrapper's local changes are not pushed to those public upstream
repositories; contact the distributor for its corresponding source.

No personal vehicle enrollment keys, account tokens, update-signing private
keys, vehicle-extracted SDK or original head-unit program dumps are included.
