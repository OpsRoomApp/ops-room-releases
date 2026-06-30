# OPS ROOM v0.22.0

OPS ROOM v0.22.0 is a release-candidate build focused on updater support, storage safety, OBS Tools layout improvements, and public packaging cleanup.

## Highlights

- Added GitHub-based updater support
- Added user-confirmed update prompt
- Added separate OPS ROOM Updater executable for safer replacement
- Added SHA256 verification before update install
- Added log rotation to prevent oversized OPS ROOM logs
- Added local storage cleanup actions for logs and cache
- Fixed OBS Tools / Overlay Studio layout clipping
- Improved public README and release notes
- Preserved validated GSX automation flow from v0.21.0 RC

## Validated GSX Automation

The existing validated GSX automation flow was not intentionally changed in this release.

Validated status:

- Fenix: working perfectly with HAR-matched Airbus/Fenix GSX loading flow
- FSLabs: working with the same flow
- iniBuilds: catering, refuelling, boarding/loading working
- PMDG 777W/PMDG: working correctly after importing SimBrief/OFP inside PMDG EFB first
- iFly: working, pushback tug attaches automatically
- Aerosoft: not retested for this release, expected compatible, manual door opening/closing may be required

## Important PMDG Note

PMDG users must import the SimBrief OFP inside the PMDG EFB before starting OPS ROOM GSX automation.

If the OFP is not imported in the PMDG EFB first, GSX can target incorrect or near-full fuel.

## Updater Notes

OPS ROOM v0.22.0 includes the first GitHub updater flow.

The updater checks the public OPS ROOM release manifest, compares the installed version, prompts the user, downloads the approved release ZIP, verifies the SHA256 checksum, stages the update, closes OPS ROOM, replaces the app files, and restarts the app.

Updates are user-confirmed, not silent.

## Browser Access

OPS ROOM uses port 8080:

```text
http://localhost:8080
```

For LAN devices:

```text
http://YOUR-PC-IP:8080
```

Port 8083 is not OPS ROOM. Port 8083 belongs to Fenix.

## Known Limitations

- Full silent background update is not enabled
- Updates require user confirmation
- The app is not code-signed yet, so some antivirus tools may still warn on the package
- Aerosoft aircraft may require manual door opening/closing
- Source code is not included in public releases
