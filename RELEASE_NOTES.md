# OPS ROOM v0.23.0 Public Beta RC1

Release candidate for public beta testing.

Do not publish this build to the normal GitHub updater channel until it has been smoke-tested locally and the final compiled Windows ZIP URL plus SHA256 checksum are ready.

## Public beta position

OPS ROOM is free during public beta.

Support via **Buy me a coffee** is optional and does not unlock extra features during beta:

```text
https://buymeacoffee.com/exzonom
```

Some features, licensing, pricing, availability, and packaging may change before the final v1.0 release.

## Highlights

- Floating **MSFS 2024 Camera Bridge** panel on the VATSIM FIDS page.
- Camera modes: Tail Follow, Left Spotter, Right Spotter, Front 3/4, Tower Static, and Orbit.
- Camera controls: distance, height, side offset, pitch, orbit angle, smoothing, reset view, recenter, start bridge, and release camera.
- Scratchpad TYPE / PEN / ERASER modes, with TYPE as the default.
- App-wide **Buy me a coffee** link near the Report Bug area.
- Public beta README, release notes, listing draft, and smoke-test checklist.
- GSX automation intentionally untouched in this release-candidate pass.

## RC1 changes

### Camera Bridge

- Fixed the release path so **Stop Watching / Release Camera** attempts to return the camera to the user aircraft before releasing camera ownership.
- Added a reacquire retry path after MSFS Addons camera owner loss or disable/enable.
- Hardened Start Bridge path detection for source, PyInstaller, one-folder, and `_internal` layouts.
- Kept the camera-control surface on the FIDS page rather than burying it in System.
- Preserved the previous target-parser fix so metadata keys such as `updated_at` are not treated as aircraft targets.

### Scratchpad

- TYPE mode is the default.
- Canvas pointer events are disabled in TYPE mode so text fields can receive focus and keyboard input.
- PEN and ERASER modes keep the canvas interactive for handwriting.
- The fix is intended to work on desktop browsers and touch/tablet use.

### Public beta polish

- Added **Buy me a coffee** link:

```text
https://buymeacoffee.com/exzonom
```

- Added public beta wording: free during beta, optional support, future pricing/licensing may change.
- Added release-candidate smoke-test checklist.
- Updated repository-facing documentation.

## Known limitations

- The MSFS 2024 Camera Bridge is still alpha-level and requires real tester validation.
- The Windows Camera Bridge executable must be built on Windows with Visual Studio and the MSFS/SimConnect SDK.
- The compiled public beta Windows ZIP must be smoke-tested before Flightsim.to upload.
- MSFS 2020 native camera follow remains intentionally disabled.
- GSX behaviour can vary depending on aircraft, scenery, door state, payload manager, and GSX menu timing.
- PMDG users must import the SimBrief OFP in the PMDG EFB before using OPS ROOM GSX automation.
- Windows antivirus products may flag unsigned beta builds.

## Smoke-test checklist before public upload

1. Start OPS ROOM and open the browser UI.
2. Open VATSIM FIDS and confirm the floating Camera Bridge panel appears.
3. Start the Camera Bridge from the FIDS panel.
4. Select an aircraft and confirm MSFS 2024 camera follows the correct target.
5. Confirm the Camera Bridge log shows an aircraft callsign or SimObject ID, not `updated_at`.
6. Press Stop Watching / Release Camera and confirm the view returns to the user aircraft.
7. Select another aircraft without restarting the bridge.
8. Disable/Enable the MSFS Addons camera panel and confirm recovery.
9. Test Scratchpad typing, PEN, and ERASER.
10. Confirm Buy me a coffee opens `https://buymeacoffee.com/exzonom`.
11. Confirm GSX flows are unchanged.
12. Confirm the final Windows release ZIP SHA256 matches the published checksum.

## Package notes

This RC1 project package contains source/project files for the release-candidate line.

The final public beta upload should use the compiled Windows release ZIP generated on the Windows/MSFS dev machine, not the project/source ZIP.
