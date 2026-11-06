# MGU-SSH updates

Signed update artifacts for the MGU-SSH Windows client.

## 1.0.10 green build

Release `v1.0.10` is a **prerelease**. It keeps the previously tested bundle:
cluster-render 0.4.1 with the capsule-shaped map clip, waze-on-cluster 0.9.1
and robertn_waze_cluster 0.6.1. It does not include the local contour-clip
experiment. The desktop package has passed the Windows launch check, package
CRC/component-hash verification and asset-completeness checks, but has not
completed a real-vehicle install or cold-boot acceptance test. It is not a
promise that every vehicle will be free of restart loops. Updating the PC
software alone does not repair files already installed on a head unit.

- `latest.json` / `latest.json.sig`: the Ed25519-signed update manifest.
- Releases: versioned full and update Windows packages, SHA-256 sidecars and
  the signed manifest. Both packages include all 8 fixed `data/assets` input
  files and have identical contained file bytes.
- The fixed SSH/debug assets include upstream static key/certificate material;
  they are not personal vehicle enrollment keys or the update-signing key.
- The client verifies the manifest signature and package SHA-256.
- 1.0.10 is an optional update: `minimum` remains 1.0.5. It does not raise the
  mandatory-update floor.

The desktop installer wrapper is locally maintained. The bundled
cluster-render 0.4.1, waze-on-cluster 0.9.1 and robertn_waze_cluster 0.6.1
artifacts are the previously tested local builds. The installer skips
components older than the versions already on the head unit.

Source projects and licenses:

- idrive7-8-ssh-root: https://github.com/cauliflowermossgrape/idrive7-8-ssh-root
- idrive-apps: https://github.com/robertnisipeanu/idrive-apps
- mgu-store: https://github.com/robertnisipeanu/mgu-store

GPL-3.0-or-later / MPL-2.0 and third-party notices are included in the package.
The desktop wrapper's local changes are not pushed to those public upstream
repositories; contact the distributor for its corresponding source.

No personal vehicle enrollment keys, account tokens, update-signing private
keys, vehicle-extracted SDK or original head-unit program dumps are included.
