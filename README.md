# LightKeeper

**Current Version: 0.2.5**

LightKeeper is a desktop application for planning and managing work on US Coast Guard Aids to Navigation (ATON). It downloads official Light List data from USCG NAVCEN and provides tools to browse, search, select, and generate multi-day trip workplans.

Download the latest `LightKeeper.exe` from the [Releases](https://github.com/ArsenalRX/lightkeeper-releases/releases) page — no installation required, just run it.

---

## Features

### Interactive ATON Map
- Browse lights, buoys, daybeacons, and bridges across all USCG districts
- Search by aid name or Light List number
- Filter by aid type
- Sync official data directly from USCG NAVCEN

### Trip Workplan Generator
- Smart geographic clustering into daily work areas
- Route optimization (nearest-neighbor ordering)
- Distance and time estimates per day and per leg
- Departure and arrival city routing
- Trip phases: Trailering + Water or Water Only
- Save workplan as HTML

### Lodging Intelligence
- Hotel recommendations with 10-step auto-optimization
- Lodging subtype classification: Hotel, Motel, Resort, Airport Hotel, Campground
- Airport hotel detection and filtering
- Hotel-to-ramp transit and multi-night lodging chain optimization

### Boat Ramp Finder
- Surface type display (concrete, gravel, dirt)
- Fee awareness
- Smart naming from nearby parks, campgrounds, and recreation areas
- Quality scoring (verified/likely/unverified)

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

### 38 Accuracy Checks
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

## What's New in v0.2.5

### Zulu Time Calculator Improvements
- **24-hour military time input** — times always display as `HH:MM` (e.g. `22:19`) regardless of browser or OS locale
- **Total duration display** — shows elapsed time between arrive and depart (handles overnight spans)
- **Military format output** — Zulu times now show both `HH:MMZ` and no-colon `HHMMZ` format (e.g. `22:19Z (2219Z) Zulu`)

---

## Recent Changelog

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
