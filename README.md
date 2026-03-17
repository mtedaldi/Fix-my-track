# Fix My Track 🗺️

![Version](https://img.shields.io/badge/version-v0.2.0-blue)

A collection of browser-based tools to repair and clean up GPS activity files (`.tcx`) recorded with Garmin watches and other devices.

**No installation. No server. No data leaves your device.**

---

## Tools

### 📋 TCX Pause Editor — `v0.1.0`
[`pause-editor/index.html`](pause-editor/index.html)

A lightweight tool for inspecting and cleaning up pause events in a `.tcx` file. Detects gaps in the track (based on time between trackpoints) as well as Lap/Event markers set by the watch. You can delete pauses, adjust their boundaries, or cut them out entirely to restore time continuity.

**Use this when:** you want to clean up a recording without worrying about the map — just remove pauses, fix the timeline, export.

---

### 🗺️ Fix My Track — `v0.2.0`
[`fix-my-track/index.html`](fix-my-track/index.html)

The full tool. Displays your track on an interactive OpenStreetMap and lets you draw missing segments directly on the map. Timestamps for new points are interpolated from the pace in the 30 seconds surrounding the gap.

**Use this when:** you forgot to resume your watch mid-run and want to reconstruct the missing segment by tracing it on the map.

---

## The Problem

You're out running. You stop to take a photo, pause your watch — and forget to resume it. The GPS data for those missing minutes is gone. The track before and after the gap is intact, but the recording has a hole in it.

*Fix My Track* lets you trace the missing route on a map and exports a repaired `.tcx` file with interpolated trackpoints — ready to upload to Garmin Connect, Strava, or similar.

---

## Usage

1. Download the tool you need (single `.html` file, no dependencies)
2. Open it in any modern browser (Chrome, Firefox, Safari)
3. Load your `.tcx` file
4. Identify and fix gaps
5. Export the repaired file

---

## Limitations

- Interpolated trackpoints contain **position and timestamp only** — heart rate, cadence, and elevation are not fabricated
- Distance fields in the exported file may be slightly off depending on the original recording
- Tested with Garmin Forerunner/Fenix `.tcx` exports; other devices may vary

---

## Changelog

### v0.2.0 — Fix My Track
- Interactive map view (OpenStreetMap via Leaflet)
- Draw missing segments by clicking on the map
- Pace-aware timestamp interpolation from surrounding 30s context
- Gap markers with numbered badges on the map

### v0.1.0 — TCX Pause Editor
- Drag & drop `.tcx` loading
- Automatic gap detection (time gaps + Lap/Event markers)
- Timeline visualisation
- Delete, restore, and edit pause boundaries
- Three export actions: mark only / cut out / interpolate

---

## About this project

This tool was built by [mtedaldi](https://github.com/mtedaldi) in a conversation with [Claude](https://claude.ai) (Anthropic), an AI assistant. The development process was collaborative: I described the problem, we worked through the technical approach together, and Claude wrote the code. I tested, gave feedback, and steered the direction.

I think it's important to be transparent about this. AI was not used to polish a README or generate boilerplate — it was the primary means of building the tool. The ideas, the use case, and the decisions about what matters are mine; the implementation emerged from a dialogue.

This is increasingly how software gets built, and I see no reason to hide it.

---

## Contributing

Bug reports and pull requests are welcome. If you use a different GPS device and find compatibility issues, please open an issue with an anonymised sample file.

## License

MIT — do what you want, attribution appreciated.
