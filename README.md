# OPS ROOM Releases

Official public release channel for OPS ROOM.

OPS ROOM is a local-first flight operations companion for Microsoft Flight Simulator. It brings dispatch, briefing, flight monitoring, network tools, GSX ground handling, announcements, OBS overlays, and browser-based cockpit or stream use into one LAN-friendly interface.

This repository hosts compiled OPS ROOM release packages, release notes, checksums, and update metadata only.

Source code is not published here.

## Downloads

Public OPS ROOM builds are published from the **Releases** section of this repository.

Each release may include:

- OPS ROOM Windows x64 ZIP package
- SHA256 checksum file
- Release notes
- Update metadata used by the app updater

Download the latest release from:

https://github.com/OpsRoomApp/ops-room-releases/releases

## Updates

OPS ROOM can use this repository to check for available updates.

When a newer version is available, OPS ROOM shows an update prompt. Updates are user-confirmed, not silent. The app downloads the approved release package, verifies its checksum, closes OPS ROOM, runs the updater, replaces the application files, and restarts OPS ROOM.

User data is stored separately in Windows AppData and is not part of the public release ZIP.

Typical preserved user data includes:

- settings
- secrets/API keys
- SimBrief data
- logbook database
- dispatch selections
- local diagnostics and logs

## Browser Access

OPS ROOM runs locally on the PC and serves its browser interface over the LAN.

Local address:

```text
http://localhost:8080
```

LAN device address:

```text
http://YOUR-PC-IP:8080
```

Port `8083` is not OPS ROOM. Port `8083` belongs to Fenix.

## Announcement Packs

Default announcements are stored inside the installed OPS ROOM folder:

```text
OPS ROOM\Announcements\Default\
```

Airline-specific announcement packs can be added separately. If a selected airline pack is missing, OPS ROOM falls back to the default announcement pack and shows a friendly Announcer notice.

For support, bug reports, announcement packs, and community updates, join the OPS ROOM Discord:

https://discord.com/invite/ZqZSSfeW9W

## PMDG Note

PMDG users must import the SimBrief OFP inside the PMDG EFB before starting OPS ROOM GSX automation.

If the OFP is not imported in the PMDG EFB first, GSX can target incorrect or near-full fuel.

## Proprietary Software Notice

OPS ROOM is proprietary software.

Downloading OPS ROOM does not grant permission to copy, modify, reverse engineer, redistribute, repackage, sell, publish, or derive competing software from OPS ROOM without written permission from the author.

This repository exists only to distribute approved compiled releases and update metadata.
