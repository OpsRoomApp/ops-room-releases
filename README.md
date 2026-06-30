# OPS ROOM Releases

Official public release channel for OPS ROOM.

OPS ROOM is a local-first flight operations companion for Microsoft Flight Simulator, built for dispatch, briefing, network monitoring, GSX ground handling, announcements, OBS overlays, and browser-based cockpit/stream use over LAN.

This repository hosts compiled OPS ROOM release packages, release notes, checksums, and update metadata only.

Source code is not published here.

## Downloads

Public release packages are published under the **Releases** section of this repository.

Each release package includes:

- OPS ROOM Windows application package
- README.txt
- RELEASE_NOTES.txt
- Required runtime folders
- Versioned checksum file

## Updates

OPS ROOM may use this repository to check for available updates.

The app checks the public update manifest, compares the installed version, and prompts the user before downloading and installing a newer release.

Updates are user-confirmed. OPS ROOM does not silently replace itself while you are flying.

## Important Notes

OPS ROOM runs locally on your PC and serves the browser interface over your LAN.

Default browser address:

```text
http://localhost:8080
