# LightKeeper — USCG ATON Workplan Tool

**Version 0.8.9.4** | Proprietary Software — All Rights Reserved

LightKeeper is a desktop application for planning and managing work on US Coast Guard Aids to Navigation (ATON). It downloads official Light List data from USCG NAVCEN and provides tools to browse, search, select, and generate multi-day trip workplans with an advanced logic engine.

## Features

### ATON Data & Map
- Browse lights, buoys, daybeacons, and bridges across all 9 USCG districts on an interactive map
- Multiple map layers: Google Satellite, Esri, OpenStreetMap, Topo, NOAA ENC charts
- Search by aid name or Light List number, filter by type
- Sync official GeoJSON data from USCG Navigation Center (NAVCEN)
- Save and manage Areas of Responsibility (AORs)
- Aid notes system for per-aid annotations

### Trip Workplan Generator
- Smart geographic clustering with sequential waterway partitioning
- Route optimization with 2-opt, waterway linear ordering, and recovery ramp end-bias
- Waterway tortuosity factor (auto-computed from aid GPS — accounts for river bends)
- Per-aid work time estimation using characteristics, RACON, AIS, optics, range, height, and remarks
- Full day time budget: launch/recovery prep, ramp transit, approach/departure, work, contingency buffer
- Joint ramp optimization: evaluates top 3 launch x top 3 recovery ramps (9 combinations)
- Barrier-aware ramp scoring (dams, locks, weirs detected via OpenStreetMap)
- Tight cluster detection (aids <0.5mi apart never split across days)
- Hotel recommendations with multi-night preference scoring and lodging subtype classification
- OSRM real road distances throughout optimization pipeline
- Trip phases (Trailering + Water or Water Only)
- Vessel config integration (fuel, draft, bridge clearance checks)
- Departure and arrival city routing
- Save workplan as HTML file
- Manual workplan builder with drag-and-drop day assignment and reordering
- Trip templates — save and auto-load settings
- Equipment load list per trip

### Route Planner
- Create routes by clicking map or snapping to aids
- Save, load, and manage multiple routes
- Load multiple saved routes at once with join support
- True and magnetic compass course on each leg
- Distance (NM), ETE, and ETA per waypoint
- Cruise speed and current adjustment
- Reverse route, undo/redo waypoints
- Right-click context menu (edit, reverse, clear)
- Drag waypoints to reposition
- Route labels scale with zoom, hidden when zoomed out

### Workplan Route Map
- Color-coded aid markers per day
- Draw custom routes per day on the workplan map
- Click aids or drop waypoints anywhere
- Draggable waypoints with click-to-delete
- Distance and true/magnetic course labels per leg

### Weather & Boat Ramps
- Weather forecasts for each area with severe weather alerts (NWS API)
- Hotel finder with lodging type filters (Hotels, Motels, Resorts, Airport Hotels, Campgrounds)
- Boat ramp/marina finder with surface quality, fee info, and smart POI-based naming

### Offline Support
- Map tile caching with CDN-direct loading when online, proxy cache when offline
- Auto-precache on launch for seamless panning
- Queue-based background tile downloader

### Tools & Settings
- Zulu Time Calculator with 24hr military time, DST-aware date picker
- Vessel configuration (speed, fuel capacity, draft)
- Customizable keyboard shortcuts
- Backup/restore all settings and data
- Route import/export (JSON)
- Bug report & feature request submission
- Auto-update checker

## Districts Supported

| District | Area | Light List Volume |
|----------|------|-------------------|
| Northeast (D1) | Atlantic | I |
| East (D5) | Atlantic | II |
| Southeast (D7) | Atlantic | III |
| Heartland (D8) | Heartland | IV/V |
| Great Lakes (D9) | Atlantic | VII |
| Southwest (D11) | Pacific | VI |
| Northwest (D13) | Pacific | VI |
| Oceania (D14) | Pacific | VI |
| Arctic (D17) | Pacific | VI |

## Keyboard Shortcuts

- **F** — Toggle Aids panel
- **W** — Toggle Workplan panel
- **R** — Toggle Route planner
- **M** — Toggle measure tool
- **S** — Focus search
- **A** — Select all in view
- **Z** — Zoom to selected
- **C** — Clear selection
- **?** — Show keyboard help
- **Esc** — Close modals / cancel

All shortcuts can be customized in Settings > Keybinds.

## Data Sources

- ATON data: [USCG NAVCEN Light List](https://www.navcen.uscg.gov/light-list-annual-publication)
- Weather: National Weather Service API
- Hotels & boat ramps: OpenStreetMap / Overpass API
- Road distances: OSRM

## Recent Changes (v0.8.9.4)

- Mapbox Directions API integration — faster routing with OSRM fallback
- Mapbox token config in Settings > Charts
- Faster ENC chart loading with smaller tile sizes and longer timeout
- Much faster app restart — auto-kills previous instance, background cleanup
- Open Data Folder button in Settings > Cache
- Fixed `_MEI` temp directory warnings and Desktop clutter
- Fixed route clearing — Clear only removes from map, doesn't delete saved routes
- Removed destructive Clear All from Load Route modal
- Browser shows loading page instead of error on reconnect

## License

Proprietary — All Rights Reserved. See [LICENSE](LICENSE) for details.
