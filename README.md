# MGU-SSH updates

Signed update artifacts for the MGU-SSH Windows client.

- `latest.json` / `latest.json.sig` — the Ed25519-signed update manifest
- Releases — `MGU-SSH-Native-Update.zip`, the update-only package
  (it intentionally has no `data/assets`)

The client verifies the manifest signature and the package SHA256. Existing
installations keep their own `data/assets`; new installations use the full
package from the private distribution channel.

Source and licenses:

- idrive7-8-ssh-root: https://github.com/cauliflowermossgrape/idrive7-8-ssh-root
- idrive-apps: https://github.com/robertnisipeanu/idrive-apps
- mgu-store: https://github.com/robertnisipeanu/mgu-store

GPL-3.0-or-later / MPL-2.0 and third-party notices are included in the package.

This repository contains no private keys, user data, or BMW firmware.
