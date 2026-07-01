# OPS ROOM

**OPS ROOM** is a local operations command centre for Microsoft Flight Simulator 2020 and Microsoft Flight Simulator 2024.

It runs on your simulator PC and serves a browser-based operations interface to the same machine, another PC, an iPad, a tablet, a phone, or an OBS browser source on your local network.

This repository/release package is for the **v0.23.0 Public Beta Release Candidate**. The beta is free and intended for real-flight testing, compatibility validation, and feedback before the final v1.0 release.

## Public beta status

OPS ROOM is currently free during public beta.

The beta is provided for testing and feedback. Some features, licensing, pricing, availability, and packaging may change before the final v1.0 release. Public beta builds do not include DRM or license-key activation.

If you enjoy the project and want to support continued development, you can buy me a coffee:

**https://buymeacoffee.com/exzonom**

Support is optional and does not unlock extra features during beta.

## What OPS ROOM does

OPS ROOM is designed as a local virtual operations desk for flight simming. It brings preparation, monitoring, dispatch-style information, network flying, ground operations, announcements, overlays, and post-flight review into one interface.

Current public beta modules include:

- **Status Board**: simulator, telemetry, SimBrief, VATSIM, vPilot, Hoppie, GSX, and system status.
- **VATSIM FIDS**: airport-style departures, arrivals, and prefile board with local browser/OBS use.
- **Dispatch**: route planning context, SimBrief integration, weather, route suggestions, and operational notes.
- **Briefing**: OFP-focused briefing view for flight preparation.
- **Flight Watch**: live flight progress, route context, and phase monitoring.
- **Performance**: takeoff and landing performance planning aid for simulator use.
- **Network / Comms**: VATSIM identity, nearby controllers, radios, vPilot messaging context, and Hoppie/CPDLC workflows.
- **Live Map**: route, ownship, traffic, controller, and airport context layers.
- **Datalink**: reusable CPDLC and TELEX-style message templates.
- **Ground Control**: GSX Remote/API workflows with compatible fallback paths.
- **Announcements**: automatic and manual cabin-announcement triggers.
- **Procedures**: normal and non-normal procedure/checklist support.
- **Scratchpad**: typed notes plus handwriting with TYPE, PEN, and ERASER modes.
- **Logbook / PIREP**: flight log, debrief, and PIREP export support.
- **OBS Tools**: browser-source overlays for streaming and recording.
- **System / Host tools**: diagnostics, LAN access, QR pairing, logs, and local storage maintenance.

## MSFS 2024 Camera Bridge alpha

v0.23.0 includes an experimental **MSFS 2024 Camera Bridge**.

When a VATSIM FIDS row is selected, OPS ROOM can send that aircraft as the active camera target. In MSFS 2024, the bridge attempts to acquire the add-on camera and follow the matched non-user SimObject.

The floating Camera Bridge panel is available on the VATSIM FIDS page and includes:

- Tail Follow
- Left Spotter
- Right Spotter
- Front 3/4
- Tower Static
- Orbit
- distance
- height
- side offset
- pitch
- orbit angle
- smoothing
- start bridge
- stop watching / release camera
- reset view
- recenter
- log/status view

MSFS 2020 remains intentionally disabled for native camera follow because the required add-on camera API path is not available there. Target matching may still run, but OPS ROOM does not attempt native camera movement in MSFS 2020.

Tester logs are written to:

```text
%LOCALAPPDATA%\Ops Room\logs\camera_bridge_2024.log
```

## GSX automation status

Validated in the current release line:

- **Fenix**: working with HAR-matched Airbus/Fenix GSX loading flow.
- **FSLabs**: working with the same flow.
- **iniBuilds**: catering, refuelling, and boarding/loading working.
- **PMDG 777W / PMDG**: working after SimBrief/OFP import inside the PMDG EFB first. Pushback tug attaches after boarding.
- **iFly**: working. Pushback tug attaches automatically.
- **Aerosoft**: not retested in this cycle. Expected compatible, but manual door opening/closing may be required.

Important PMDG rule:

Before using OPS ROOM GSX automation with PMDG, import the SimBrief OFP inside the PMDG EFB first. If this is not done, GSX can target near-full fuel instead of the correct OFP fuel state.

OPS ROOM uses the official GSX Remote/API when available and falls back to compatible GSX menu control where needed.

## Installation

1. Download the compiled OPS ROOM Windows release ZIP.
2. Extract the full folder. Do not move files out of `_internal`.
3. Run:

```text
OPS ROOM.exe
```

4. Complete the Host setup page on first launch.
5. Configure only the integrations you actually use.
6. Keep OPS ROOM open while flying.

OPS ROOM stores personal settings, secrets, dispatch state, logbook, diagnostics, and local runtime data in:

```text
%LOCALAPPDATA%\Ops Room\
```

Updating the application folder does not delete your saved settings, logbook, or secrets.

## Browser and LAN use

OPS ROOM uses port **8080**.

Local browser:

```text
http://127.0.0.1:8080
```

Host setup console:

```text
http://127.0.0.1:8080/host
```

VATSIM FIDS board:

```text
http://127.0.0.1:8080/vatsim-fids
```

OBS overlay source:

```text
http://127.0.0.1:8080/obs
```

Do not use port **8083** for OPS ROOM. Port 8083 belongs to Fenix.

For LAN/iPad use, enable LAN access in OPS ROOM Host settings. OPS ROOM will show the local network address and QR code. Keep the simulator PC and the second device on the same network.

For OBS, add a Browser Source and paste the URL generated in OBS Tools / Overlay Studio.

## Announcements

Default announcements must be located here:

```text
OPS ROOM\Announcements\Default\
```

This folder is outside `_internal` by design.

If an airline-specific pack is missing from the selected/user folder, OPS ROOM falls back to the default announcement pack.

Announcement packs, support, and community updates:

```text
https://discord.com/invite/ZqZSSfeW9W
```

## Updates

OPS ROOM includes a GitHub-based updater flow, but this **public beta release candidate must not be pushed to the normal stable update channel until smoke testing is complete**.

For RC1:

- Use manual ZIP distribution for tester validation.
- Keep the normal update channel safe until the final public beta package is confirmed.
- Do not publish a manifest with a download URL until the final compiled Windows ZIP and SHA256 checksum are ready.

The public updater repository is intended only for compiled packages, checksums, release notes, and update metadata. Source code is not intended for public release.

## Bug reporting

Use the **REPORT BUG** button inside OPS ROOM.

A useful bug report includes:

- aircraft and airport
- simulator version if known
- what button or automation was used
- what you expected to happen
- what actually happened
- screenshots or exact messages if relevant

Diagnostics are redacted before export. The report includes recent log lines only, not the full log file.

## Known limitations

- OPS ROOM is a beta/release-candidate tool and should be monitored during active flights.
- The MSFS 2024 Camera Bridge is still alpha-level and needs tester validation across aircraft, airports, and traffic situations.
- Start/release/reacquire behaviour for the Camera Bridge must be smoke-tested before public upload.
- GSX behaviour can vary with aircraft state, scenery, doors, payload manager, and GSX menu timing.
- PMDG requires SimBrief/OFP import inside the PMDG EFB before OPS ROOM GSX automation.
- Aerosoft was not retested in this cycle and may need manual door handling.
- Performance calculations are simulator planning aids, not certified aircraft performance data.
- Windows antivirus products may still flag unsigned beta packages.

## Public beta policy

OPS ROOM is free during public beta. Beta builds are intended for testing and feedback.

When OPS ROOM reaches a stable v1.0 release, future stable releases may become paid. Public beta users will keep access to the beta builds they already downloaded. Active beta testers may receive a Founder discount or complimentary license.

## License / use

OPS ROOM is proprietary software. This release package is provided for testing and use by the author/community.

Do not copy, modify, reverse engineer, redistribute, repackage, sell, or publish OPS ROOM without written permission from the author.

## Disclaimer

OPS ROOM is an independent flight-simulation companion app. It is not affiliated with Microsoft, Asobo, VATSIM, Navigraph, SimBrief, FSDreamTeam, PMDG, Fenix, FSLabs, iniBuilds, Aerosoft, iFly, or any aircraft/scenery vendor.

OPS ROOM is for entertainment and flight-simulation use only.
