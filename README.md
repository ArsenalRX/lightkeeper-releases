# LightKeeper

**Current Version: 1.0.0**

LightKeeper is a desktop application for planning and managing work on US Coast Guard Aids to Navigation (ATON). It downloads official Light List data from USCG NAVCEN and provides tools to browse, search, select, and generate multi-day trip workplans with an advanced logic engine for accurate time, distance, and route planning.

Download the latest `LightKeeper.exe` from the [Releases](https://github.com/ArsenalRX/lightkeeper-releases/releases) page — no installation required, just run it.

---

## Features

### Interactive ATON Map
- Browse lights, buoys, daybeacons, and bridges across all USCG districts
- Search by aid name or Light List number
- Filter by aid type
- Sync official data directly from USCG NAVCEN

### Trip Workplan Generator
- Smart geographic clustering with sequential waterway partitioning
- Route optimization with 2-opt, waterway linear ordering, and recovery ramp end-bias
- Waterway tortuosity factor (auto-computed from aid GPS — accounts for river bends)
- Per-aid work time from characteristics, RACON, AIS, optics, range, height, and remarks
- Full day time budget: launch/recovery prep, ramp transit, approach/departure, contingency buffer
- Joint ramp optimization: evaluates top 3 launch x top 3 recovery ramps (9 combinations)
- Barrier-aware ramp scoring (dams, locks, weirs detected via OpenStreetMap)
- Tight cluster detection (aids <0.5mi apart never split across days)
- OSRM real road distances throughout the optimization pipeline
- Detailed per-day time breakdown (collapsible): drive, prep, ramp transit, work+transit, buffer
- Departure and arrival city routing
- Trip phases: Trailering + Water or Water Only
- Save workplan as HTML

### Lodging Intelligence
- Hotel recommendations with multi-night preference scoring
- Lodging subtype classification: Hotel, Motel, Resort, Airport Hotel, Campground
- Airport hotel detection and filtering
- Hotel-to-ramp transit and multi-night lodging chain optimization

### Boat Ramp Finder
- Surface type display (concrete, gravel, dirt)
- Fee awareness
- Smart naming from nearby parks, campgrounds, and recreation areas
- Quality scoring (verified/likely/unverified)
- Waterway name matching bonus for same-waterway ramps

### Vessel Configuration
- Multi-vessel support with full spec sheets
- Honda BF150 fuel consumption curve with ECOmo lean-burn modeling
- Fuel range estimation, bridge clearance checks, draft warnings
- 26' TANB preset with all specs included

### Zulu Time Calculator
- Local-to-Zulu (UTC) time conversion
- 24-hour military time input
- Total duration between arrive and depart times
- Military format output (e.g. `2219Z`)
- Automatic DST detection for any date using IANA timezones

### Accuracy Checks
- Route distance and time validation
- Severe weather and daylight warnings
- Fuel capacity and range checks
- Bridge clearance vs. vessel height
- Ramp surface quality warnings for wet months
- Hotel-to-ramp morning commute checks
- Work time balance across days
- Crew/passenger capacity validation

### Weather
- Auto-populated forecasts from the National Weather Service
- Severe weather alerts per work area

### Other
- Auto-update with version checking
- Dark theme UI
- Collapsible workplan with interactive hotel/ramp pickers
- Bug report and feature request submission from the app

---

## What's New in v1.0.0

### Logic Engine Rework
- **Waterway tortuosity factor** — auto-computed from aid GPS positions along waterways, accounts for river bends in all distance/time calculations
- **Per-aid work time estimation** — uses aid characteristics (Fl, Iso, Oc, Q), RACON (+10min), AIS (+5min), range >10NM (+5min), height >60ft (+5min), destroyed/missing aids (5min verify only)
- **Full day time budget** — launch prep (25min), ramp-to-first-aid transit, work+transit, last-aid-to-ramp transit, recovery prep (25min), 45min contingency buffer
- **Sequential waterway partitioning** — replaces k-means for river trips, splits at natural gaps along the waterway
- **Joint ramp optimization** — evaluates top 3 launch x top 3 recovery ramps (9 combos), picks lowest total day time
- **Barrier-aware ramp scoring** — detects dams, locks, weirs via OpenStreetMap Overpass API, penalizes ramps separated from aids by barriers
- **Tight cluster detection** — aids <0.5mi apart are never split across different days
- **OSRM before optimization** — real road distances used throughout the entire optimization pipeline
- **Multi-night hotel preference** — jointly scores hotels for consecutive days with nearby ramps
- **Detailed time breakdown UI** — collapsible per-day view showing morning drive, launch prep, ramp transit, work+transit, recovery prep, evening drive, shuttle, buffer
- **Code cleanup** — removed duplicate functions, redundant imports, fixed name collisions

---

## Recent Changelog

### v0.2.5
- Zulu calculator: 24hr military time input, total duration, military format output (HHMMZ)

### v0.2.4
- Fixed auto-update system
- Renamed Zulu Time Calculator button

### v0.2.3
- Lodging subtype classification (Hotel, Motel, Resort, Airport Hotel, Campground)
- Airport hotel filtering
- Zulu Time Calculator with DST detection
- Smart boat ramp naming from nearby POIs
- Ramp surface type and fee display
- 38 accuracy checks (up from 29)
- 10-step auto-optimization (airport hotel deprioritization, lodging chain optimization)

### v0.2.2
- Dark theme workplan redesign with collapsible days
- Hotel picker and aid skip/remove controls
- Batch trip context API for faster generation
- Overpass caching and parallel weather fetching
- Filtered out closed/abandoned/private locations

### v0.2.1
- Fixed workplan hotel/launch/weather queries
- Fixed city geocode lookup failures
- Auto-update improvements (no more .bak files)
- Update notification with "Update Now" button

---

## Data Sources

- **ATON**: [USCG Navigation Center Light List](https://www.navcen.uscg.gov/light-list-annual-publication)
- **Weather**: National Weather Service API
- **Hotels & Boat Ramps**: OpenStreetMap / Overpass API
- **Road Distances**: OSRM (Open Source Routing Machine)
