# LightKeeper Changelog

All notable changes to LightKeeper are documented here, organized by version.

---

## v0.8.9.5 (April 10, 2026)

### New Features
- **Tides & Water Levels** — right-click map to search nearby water stations from NOAA CO-OPS (tides, currents), USGS NWIS (river/stream gages), and USBR RISE (reservoirs like Lake Roosevelt/Grand Coulee)
- **Clickable station markers** — left-click any water station marker to load detailed data (tide predictions, reservoir elevation, gage readings)
- **Route backbone snapping** — workplan Route Map follows saved routes along waterways instead of drawing straight lines across land
- **Auto Route button** — one-click to connect all aids for a day, snapping to saved routes if available
- **Select All moved to Aids Browser** — "Select All" button now in each tab's header; auto-opens workplan panel after selection

### Improvements
- **Smarter Distribute** — auto-optimizes after distributing: border smoothing between adjacent days, hours balancing, route reordering (removed separate Optimize button)
- **Responsive toolbar** — wraps to 2 rows on smaller screens (e.g. 1920x1200) with dynamic map/panel adjustment via ResizeObserver
- Dashed route lines when no saved route available (visual cue for unverified paths)
- Route status bar shows "(on saved route)" or "(straight line)"

### Fixes
- Fixed version display mismatch across UI

### Removals
- Removed Optimize button from Manual Builder (functionality merged into Distribute)
- Removed Select All from workplan panel (moved to Aids Browser)

---

## v0.8.9.4 (April 4, 2026)

### Fixes
- Added third Overpass API fallback server for improved reliability
- Fixed silent weather/tide/sunrise task failures in workplan generation

---

## v0.8.9.3 (April 2026)

### New Features
- **District picker** — jump to any USCG district from toolbar dropdown
- **Extended aid data** — expanded ATON data fields for detailed aid info
- **CDN tile loading** — direct CDN tiles when online for faster map rendering

### Improvements
- Improved map tile loading performance
- Better district-level navigation

---

## v0.8.9.3 (April 2026)

### New Features
- **District picker** — jump to any USCG district from toolbar dropdown
- **Extended aid data** — expanded ATON data fields for detailed aid info
- **CDN tile loading** — direct CDN tiles when online for faster map rendering

### Improvements
- Improved map tile loading performance
- Better district-level navigation

---

## v0.8.9.2 (April 2026)

### New Features
- **Mapbox Directions API** — real road routing with OSRM fallback for workplan travel distances
- **Mapbox token config** — configurable in Settings > Charts

### Improvements
- More accurate road distance calculations throughout optimization pipeline
- Fallback to OSRM when Mapbox unavailable

---

## v0.8.9.1 (April 2026)

### Changes
- Switched to 4th-number patch versioning scheme (0.8.9.X)
- Minor stability improvements

---

## v0.8.9 (March 2026)

### New Features
- **Open Data Folder button** in Settings > Cache
- Faster ENC chart loading with smaller tile sizes and longer timeout

### Improvements
- Much faster app restart — auto-kills previous instance, background cleanup
- Disabled debug mode and reloader in frozen exe

### Fixes
- Fixed route clearing — Clear only removes from map, doesn't delete saved routes
- Removed destructive Clear All from Load Route modal
- Browser shows loading page instead of error on reconnect
- Fixed sync failures caused by debug mode in frozen exe

---

## v0.8.8 (March 2026)

### Fixes
- Fixed `_MEI` temp directories appearing on Desktop
- Added atexit cleanup for PyInstaller temp directory
- Auto-dismiss `_MEI` cleanup warning dialog
- Switched to console mode with hidden window to suppress warnings

---

## v0.8.7 (March 2026)

### Changes
- Updated copyright holder in LICENSE
- Updated copyright to Evan Isakson in About section
- Check both repos for updates
- Removed all lightkeeper-releases references from source, fixed runtime-tmpdir

---

## v0.8.6 (March 2026)

### Fixes
- Fixed tutorial checkbox persistence
- Added X close button to tutorial
- Suppress `_MEI` warning dialog
- Use releases repo for update checks

---

## v0.8.5 (March 2026)

### New Features
- **UX overhaul** — styled modals, improved visual design throughout
- **Route planner upgrades** — improved waypoint management, context menus
- **Interactive tutorial** — first-run guided walkthrough

### Improvements
- Modernized modal dialogs
- Better route planner ergonomics

---

## v0.2.5 (February 2026)

### Improvements
- **Zulu calculator** — 24hr military time input, duration display, improved format

---

## v0.2.4 (February 2026)

### Fixes
- Fixed update batch script — writes to correct app directory, self-deletes properly

---

## v0.2.3 (February 2026)

### New Features
- **Lodging classification** — hotels, motels, resorts, airport hotels, campgrounds
- **Airport hotel filtering** — exclude or include airport hotels
- **Zulu Time Calculator** — military time conversion tool

### Improvements
- 38 accuracy checks across workplan generation
- Better lodging subtype detection

### Fixes
- Fixed auto-update system
- Renamed Zulu button for clarity

---

## v0.2.2 (February 2026)

### New Features
- **Dark theme workplan** — redesigned workplan output with interactive features
- **Cancel button** — cancel workplan generation mid-process
- **Batch trip context API** — faster hotel/ramp/weather lookups

### Improvements
- Simplified workplan header — only departure and arrival city
- Removed fuel stops stat and lookup error messages

---

## v0.2.1 (February 2026)

### Fixes
- Fixed auto-update — no more `.bak` files on desktop
- Fixed PyInstaller temp directory warning dialog
- Fixed: show no aids when no districts enabled instead of showing all

---

## v0.2.0 (January 2026)

### New Features
- **Arrival city** — route planning with departure and arrival cities
- **Update notification** — shows Update Now button instead of auto-downloading
- **Geocode retry** — automatic retries on geocode failure with longer timeout

### Improvements
- Better hotel search reliability
- Cleaned trip summary header
- Per-day queries with rate limiting for hotel/launch/weather

### Fixes
- Fixed geocode lookup with retries, longer timeout, proper User-Agent
- Fixed workplan hotel/launch/weather per-day queries

---

## v0.1.0 (January 2026)

### Fixes
- Fixed longitude wrapping bug in bbox viewport query
- Bug fixes and stability improvements

---

## v0.0.9 (January 2026)

### Fixes
- Fixed flyToAid crash
- Fixed updateSelBadge error
- Removed error reporting UI
- Fixed black/grey map tiles — multi-subdomain Google tiles + Esri fallback
- Fixed frozen loading spinner
- Fixed white map on zoom — dark background + transparent fallback

---

## v0.0.8 (January 2026)

### New Features
- **Blocking overlay during sync** — prevents interaction during data sync
- **Auto-sync** when NAVCEN has newer Light List data on launch
- **Lighthouse icon** for EXE

### Improvements
- Removed presets (simplified UI)
- Improved stacked aids warning

---

## v0.0.7 (December 2025)

### New Features
- **Box select** — shift+drag to select aids in an area
- **Context menu** — right-click aids for quick actions
- **Trip presets** — save and load trip configurations
- **CSV export** — export aid data

### Improvements
- Auto-report errors to GitHub Issues
- Auto-shutdown server when browser tab closes
- Button toggle fixes, tighter responsive CSS

### Fixes
- Fixed white screen — replaced beforeunload shutdown with heartbeat watchdog

---

## v0.0.6 (December 2025)

### New Features
- **Responsive UI** — adapts to different screen sizes
- **GitHub update check** on launch

### Improvements
- NOAA chart layer fixes
- Single-file EXE distribution
- Store database in `%APPDATA%/LightKeeper` instead of next to EXE
- Auto-sync ATON data on first launch

### Fixes
- Fixed NOAA charts showing white — transparent fallback for missing tiles

---

## v0.0.5 (December 2025)

### New Features
- **Smart trip workplan** — time-aware clustering balances travel + work hours across days
- **Departure city** — transit distance to Day 1
- **Boat launches** — custom markers, launches tab
- **Waterway name search** — search by lake/river name
- **Start date and depart time** inputs for trip planning

### Improvements
- Production hardening
- Update checker
- NOAA charts fix
- PyInstaller build support
- Smart workplan clustering

### Fixes
- Fixed objectid collision dropping entire sync batches
- Fixed departure city geocode — API returns array not object
- Fixed hotel/launch search — single bulk query
- Improved boat launch naming — use operator/city/street
- Fixed search: strip periods for fuzzy matching

---

## v0.0.1–v0.0.4 (November–December 2025)

### Initial Development
- **Interactive map** with Leaflet — lights, buoys, daybeacons, bridges
- **USCG NAVCEN data sync** — download official Light List GeoJSON
- **Multiple map layers** — Google Satellite, Esri, OpenStreetMap, Topo, NOAA ENC
- **Search and filter** — by aid name, LL#, type
- **Trip workplan generator** — hotel, weather, and PDF export
- **Weather location search**
- **Dark theme UI** — cleaner design, compact panels
- **Click-to-fly** — click aid in sidebar to fly to it on map
- **District management** — enable/disable districts, live toggle
- **Aid deduplication** — fix duplicate entries by light list number

---

## v1.1.1 (Pre-release / Development Branch)

### New Features
- Waterway-aware routing
- Tile caching system
- Drag-drop day editing in workplan
- Calibration tools

### Removals
- Removed first-run setup wizard

---

## v1.1.0 (Pre-release / Development Branch)

### New Features
- Engine presets
- Logic priorities system
- Clustering overhaul
- Trip templates, map visualization, trip report, equipment presets

### Fixes
- Fixed JS syntax error in workplan map legend

---

## v1.0.0 (Pre-release / Development Branch)

### Major Rework
- Complete logic engine rework for accurate workplan generation
- Workplan accuracy and ease-of-use improvements

---

## Logic Engine Updates (Pre-release / Development Branch)

### Features
- Border smoothing pass to fix interleaved day assignments
- Max hours cap enforcement — rebalance aids between overloaded days
- Tidal/difficulty/barrier intelligence
- Manual workplan builder
- Waterway-aware routing, hotel scoring, modal cleanup

### Fixes
- Fixed workplan clustering hang — oscillation detection in Phases B and E
