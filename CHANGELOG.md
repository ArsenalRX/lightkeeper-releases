# LightKeeper Changelog

All notable changes to LightKeeper are documented here.

**Initial Release:** October 24, 2025

---

## v0.8.9.5 (April 10, 2026)

### New Features
- **Tides & Water Levels** — right-click map to search nearby water stations from NOAA CO-OPS (tides, currents), USGS NWIS (river/stream gages), and USBR RISE (reservoirs like Lake Roosevelt/Grand Coulee)
- **Clickable station markers** — left-click any water station marker to load detailed tide predictions, reservoir elevation/inflow/storage, or gage readings
- **Route backbone snapping** — workplan Route Map follows saved routes along waterways instead of drawing straight lines across land
- **Auto Route button** — one-click to connect all aids for a day, snapping to saved routes if available
- **Select All in Aids Browser** — moved to each tab's "N aids in view" header for better workflow; auto-opens workplan panel after selection

### Improvements
- **Smarter Distribute** — auto-optimizes after distributing: border smoothing between adjacent days, hours balancing, route reordering within each day
- **Responsive toolbar** — wraps to 2 rows on smaller/laptop screens (e.g. 1920x1200) with dynamic map and panel adjustment via ResizeObserver
- Dashed route lines when no saved route available (visual cue for unverified paths)
- Route status bar shows "(on saved route)" or "(straight line)"
- Panel drag constrained to stay below toolbar

### Removals
- Removed Optimize button from Manual Builder (functionality merged into Distribute)

---

## v0.8.9.4 (April 4, 2026)

### Fixes
- Added third Overpass API fallback server for improved reliability
- Fixed silent weather/tide/sunrise task failures in workplan generation

---

## v0.8.9.3 (April 2026)

### New Features
- **District picker** — jump to any USCG district from toolbar dropdown, priority loads selected district
- **Extended aid data** — structure description, focal plane, sound signal, color, state, CG sector, international LL#, daymark shape
- **CDN tile loading** — direct CDN tiles when online for faster map rendering with background proxy caching for offline
- **NOAA Coast Pilot** — toolbar button, per-district PDF volumes, offline caching
- **Improved aid popups** — color-coded type badge and richer detail display
- **Unified right-click context menu** on all aid markers with grouped actions

### Improvements
- Auto-backup on exit with silent restore on launch
- Map position remembered across sessions
- Status bar shows active district and aid count
- Keyboard shortcuts overlay includes Route (R)

---

## v0.8.9.2 (April 2026)

### New Features
- **Mapbox Directions API** — real road routing with OSRM fallback for workplan travel distances
- **Mapbox token config** — configurable in Settings > Charts

### Improvements
- More accurate road distance calculations throughout optimization pipeline
- Automatic fallback to OSRM when Mapbox unavailable

---

## v0.8.9.1 (April 2026)

### Changes
- Switched to 4th-number patch versioning scheme (0.8.9.X)
- Point update checker to public lightkeeper-releases repo

---

## v0.8.9 (March 2026)

### New Features
- **Open Data Folder button** in Settings > Cache
- **Faster ENC chart loading** — smaller tile sizes and longer timeout

### Improvements
- Much faster app restart — auto-kills previous instance, background MEI cleanup
- Disabled debug mode and reloader in frozen exe for stability

### Fixes
- Fixed route clearing — Clear only removes from map, doesn't delete saved routes
- Removed destructive Clear All from Load Route modal
- Browser shows loading page instead of error on reconnect
- Fixed sync failures caused by debug mode in frozen exe
- Updated version history in About section

---

## v0.8.8 (March 2026)

### Fixes
- Fixed `_MEI` temp directories appearing on Desktop
- Added atexit cleanup for PyInstaller temp directory
- Auto-dismiss `_MEI` cleanup warning dialog
- Switched to console mode with hidden window to suppress warnings
- Removed all lightkeeper-releases references from source code

---

## v0.8.7 (March 2026)

### Changes
- Updated copyright holder
- Check both repos (source + releases) for updates
- Updated copyright in About section and LICENSE file

---

## v0.8.6 (March 2026)

### Fixes
- Fixed tutorial checkbox persistence
- Added X close button to tutorial
- Suppress `_MEI` warning dialog
- Use releases repo for update checks

---

## v0.8.5 / v0.8.0 (March 2026)

### New Features
- **Logic engine overhaul** — tidal/difficulty/barrier intelligence
- **Manual workplan builder** — drag-and-drop day assignment and reordering
- **Workplan route map** — draw custom routes per day with distance/bearing labels
- **Route planner upgrades** — ETA per waypoint, multi-route loading, right-click context menu
- **Border smoothing** — fix interleaved day assignments between adjacent days
- **Max hours cap** — rebalance aids between overloaded days
- **Oscillation detection** — prevent clustering hang in balancing phases
- **In-app styled modals** — replace all browser alert/confirm dialogs
- **Template auto-load** on select, start date auto-populate
- **First-launch tutorial** — interactive guided walkthrough

### Improvements
- Waterway-aware routing throughout clustering
- Hotel scoring improvements
- Modal cleanup and visual polish

---

## v0.7.0 (March 2026)

### New Features
- **Offline map tile caching** — CDN-direct loading when online, proxy cache when offline
- **Weather forecast caching** with stale fallback
- **OSRM route caching** for offline distance calculations
- **Cache management** in Settings panel
- **District download** for full offline support
- **Auto-precache** on launch for seamless panning
- Queue-based background tile downloader

---

## v0.5.0 (February–March 2026)

### New Features
- **Trip workplan generator** — smart geographic clustering with sequential waterway partitioning
- **Route optimization** — 2-opt with waterway linear ordering and recovery ramp end-bias
- **Waterway tortuosity factor** — auto-computed from aid GPS positions (accounts for river bends)
- **Per-aid work time estimation** — based on characteristics, RACON, AIS, optics, range, height, and remarks
- **Full day time budget** — launch/recovery prep, ramp transit, approach/departure, work, contingency buffer
- **Joint ramp optimization** — evaluates top 3 launch x top 3 recovery ramps (9 combinations)
- **Barrier-aware ramp scoring** — dams, locks, weirs detected via OpenStreetMap
- **Tight cluster detection** — aids <0.5mi apart never split across days
- **Hotel recommendations** — multi-night preference scoring, lodging subtype classification (hotels, motels, resorts, airport hotels, campgrounds)
- **Boat ramp finder** — surface quality, fee info, smart POI-based naming
- **Weather forecasts** — NWS API with severe weather alerts
- **Departure and arrival city** routing
- **Trip templates** — save and auto-load settings
- **Equipment load list** per trip
- **Zulu Time Calculator** — 24hr military time, duration display

### Improvements
- OSRM real road distances throughout optimization pipeline
- Trip phases (Trailering + Water or Water Only)
- Vessel config integration (fuel, draft, bridge clearance checks)
- Batch trip context API for faster hotel/ramp/weather lookups
- Cancel button for workplan generation
- Dark theme workplan redesign with interactive features

---

## v0.2.x (January–February 2026)

### v0.2.5
- Zulu calculator — 24hr input, duration display, military format

### v0.2.4
- Fixed update batch script — writes to correct app directory, self-deletes

### v0.2.3
- Lodging classification — hotels, motels, resorts, airport hotels, campgrounds
- Airport hotel filtering
- 38 accuracy checks across workplan generation

### v0.2.2
- Dark theme workplan redesign with interactive features
- Cancel button for workplan generation
- Batch trip context API — faster lookups
- Simplified workplan header

### v0.2.1
- Fixed auto-update — no more `.bak` files on desktop
- Fixed PyInstaller temp directory warning
- Fixed: show no aids when no districts enabled

### v0.2.0
- Arrival city support
- Update notification with Update Now button
- Geocode retry with longer timeout
- Per-day hotel/launch/weather queries with rate limiting

---

## v0.1.0 (December 2025–January 2026)

### New Features
- **Interactive map** — Leaflet with lights, buoys, daybeacons, bridges
- **Multiple map layers** — Google Satellite, Esri, OpenStreetMap, Topo, NOAA ENC
- **USCG NAVCEN data sync** — download official Light List GeoJSON for all 9 districts
- **Search and filter** — by aid name, Light List number, type
- **Areas of Responsibility (AOR)** — save and manage custom regions
- **Aid notes system** — per-aid annotations
- **Waterway name search** — search by lake/river name
- **Box select** — shift+drag to select aids in an area
- **Right-click context menu** — quick actions on aids and map

### Improvements
- Click-to-fly — click aid in sidebar to zoom to it on map
- District management — enable/disable districts, live toggle
- Aid deduplication by light list number
- Responsive UI for different screen sizes

---

## v0.0.x (October–December 2025)

### Initial Development (v0.0.1–v0.0.9)
- **October 24, 2025** — Initial release
- ATON data browser with interactive Leaflet map
- USCG NAVCEN data sync (all 9 districts)
- Dark theme UI
- Single-file EXE distribution via PyInstaller
- Store database in `%APPDATA%/LightKeeper`
- Auto-sync ATON data on first launch
- Auto-report errors to GitHub Issues
- Auto-shutdown server when browser tab closes
- GitHub update check on launch
- Lighthouse icon for EXE
- Multiple map layer support
- Weather location search

### Fixes (v0.0.x)
- Fixed longitude wrapping bug in bbox viewport query
- Fixed black/grey map tiles — multi-subdomain Google tiles + Esri fallback
- Fixed frozen loading spinner
- Fixed white map on zoom
- Fixed NOAA charts showing white
- Fixed duplicate aid entries
- Fixed flyToAid crash
- Fixed white screen — heartbeat watchdog replaces beforeunload shutdown
- Fixed objectid collision dropping sync batches
- Fixed departure city geocode
- Fixed hotel/launch search — single bulk query
