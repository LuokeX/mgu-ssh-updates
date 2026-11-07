# MGU-SSH updates

Signed update artifacts for the MGU-SSH Windows client.

## 1.0.11 green build and one-click installer

Release `v1.0.11` is a **prerelease**. It is the first release that ships a
one-click installer:

- `MGU-SSH-Setup-1.0.11.exe` installs the same folder layout as the green zip,
  with the bundled Python, Node.js and OpenSSH runtime, a desktop shortcut, a
  Start Menu entry and an uninstaller. No Python, Node.js, OpenSSH or other
  environment setup is needed. The app still asks for administrator rights
  when it starts, as the green version did.
- The desktop client prefers this signed installer for its own updates and
  passes `/DIR`, so an update stays in the folder the app is running from.
  Older clients keep using the zip update path.
- The build silently installs, hash-checks every bundled component, launch-tests
  and uninstalls the package before it is accepted.

Bundled CarPlay components:

- cluster-render 0.4.4: the wide instrument-map contour redrawn on an upright
  instrument illustration, with an inward feather; the old oval remains
  available.
- waze-on-cluster 0.9.4: the Display target remembers and restores the panel
  rectangle and clip across centre/panel switches; invalid stored profiles do
  not replace the active one.
- robertn_waze_cluster 0.6.1, mgu-deploy 0.7.15, app-privacy 1.7.1.

The contour and transition were viewed on one vehicle. The desktop package has
passed the Windows launch check and the installer's silent install, launch and
uninstall checks; a full cold-boot acceptance matrix is still pending. Updating
the PC software alone does not repair files already installed on a head unit;
the installer skips components older than the ones already there.

- `latest.json` / `latest.json.sig`: the Ed25519-signed update manifest, with
  the update zip under `url`/`urls` (for older clients) and the one-click
  installer under `installer`.
- Releases: versioned full and update Windows packages, the one-click
  installer and the signed manifest. All packages include the 8 fixed
  `data/assets` input files.
- The fixed SSH/debug assets include upstream static key/certificate material;
  they are not personal vehicle enrollment keys or the update-signing key.
- The client verifies the manifest signature and the package SHA-256.
- 1.0.11 is an optional update: `minimum` remains 1.0.5. It does not raise the
  mandatory-update floor.

Source projects and licenses:

- idrive7-8-ssh-root: https://github.com/cauliflowermossgrape/idrive7-8-ssh-root
- idrive-apps: https://github.com/robertnisipeanu/idrive-apps
- mgu-store: https://github.com/robertnisipeanu/mgu-store

GPL-3.0-or-later / MPL-2.0 and third-party notices are included in the package.
The desktop wrapper's local changes are not pushed to those public upstream
repositories; contact the distributor for its corresponding source.

No personal vehicle enrollment keys, account tokens, update-signing private
keys, vehicle-extracted SDK or original head-unit program dumps are included.
