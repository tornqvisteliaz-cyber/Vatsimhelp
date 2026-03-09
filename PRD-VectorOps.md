# Product Requirements Document (PRD)

## Product name
**VectorOps**

## Category
Web platform for Microsoft Flight Simulator 2024 pilots.

## Product vision
Build a single website pilots open before every flight.

Replace scattered tools.

Give dispatch intelligence, airport data, taxi guidance, and live flight support in one interface.

### The goal
A pilot opens one tab. Plans the flight. Flies the flight. Reviews the flight.

## Primary users
- MSFS 2024 pilots
- VATSIM pilots
- ATC24 pilots
- Virtual airline pilots

## Core problem
Flight sim pilots switch between many tools.

### Example workflow today
- SimBrief for flight plan
- Navigraph for charts
- VATSIM Radar for traffic
- Airport charts PDFs
- Random websites for runway info

This wastes time and breaks immersion.

VectorOps fixes this by combining:
- Dispatch
- Airport intelligence
- Taxi routing
- Live cockpit dashboard

## Core features

### Feature 1: AI Dispatch Planner

**Purpose**  
Generate a realistic flight plan in seconds.

**Inputs**
- Departure airport
- Arrival airport
- Aircraft type
- Cruise altitude (optional)

**Outputs**
- Optimized route
- SID recommendation
- STAR recommendation
- Cruise level
- Fuel plan
- Alternate airport
- Step climb plan

**Extra**
- Wind-optimized route
- Predicted runway usage
- Predicted arrival flow

**Interface**
Large route card:

- DEP EKCH
- ARR ESSA
- Aircraft A320

Button: **Generate dispatch**

**Output page**
- Route map
- Navlog
- Fuel breakdown
- Expected runway

**Export**
- SimBrief format
- `.pln` file
- PDF dispatch release

### Feature 2: Airport Intelligence

**Purpose**  
Show real operational data for airports.

**Airport page example:** ESSA (Stockholm Arlanda)

**Sections**

**Runway usage**
- 19R/35L used 60%
- 01L/19R secondary

**Popular SIDs**
- ARS SID
- NELLI SID

**Popular STARs**
- HMR STAR
- XILAN STAR

**Traffic heatmap**
- Busiest hours
- Quiet hours

**ATC probability**
- Tower online chance
- Approach online chance

### Feature 3: Smart Taxi System

**Purpose**  
Remove taxi confusion.

**User enters**
- Gate A12
- Runway 22R

**System returns**
- Full taxi path
- Turn-by-turn instructions
- Airport map

**Example**
- Pushback
- Taxi via A B3 C
- Hold short RWY 22R

**Interface**
Interactive airport map.

### Feature 4: Live Flight Dashboard

**Purpose**  
Second screen during flight.

**Data source**
SimConnect connection to MSFS.

**Displayed data**
- Fuel remaining
- Fuel at destination
- Top of descent prediction
- Distance to TOD
- Descent rate recommendation
- Crosswind alert

Pilot sees everything on tablet or second monitor.

### Feature 5: Post Flight Analyzer

After landing, the system scores the flight.

**Metrics**
- Landing vertical speed
- Touchdown zone accuracy
- Taxi speed violations
- Fuel efficiency
- Route deviation

**Output**
Flight score out of 100.

**Example**
- Landing: -230 fpm
- Taxi violations: 2
- Fuel margin: good
- Final score: 84

Pilot logbook stores all flights.

## UI design

### Design style
Minimal airline operations style.

### Color palette
- Primary: `#0B0F14` (deep aviation black)
- Secondary: `#1B2A3A` (dark blue)
- Accent: `#4DA3FF` (aviation blue)
- Text: `#E6EDF3`

### UI components
- Glass panels
- Large airport codes
- Animated route maps
- Minimal typography

### Reference style
Airline operations dashboards.

## Pages
- Home (quick flight planner, recent flights)
- Flight planner (route generation, fuel planning)
- Airport page (runway usage, SID/STAR data)
- Taxi page (gate-to-runway planner)
- Live dashboard (real-time flight data)
- Pilot logbook (flight history, scores)

## Integrations

### SimConnect
Used for:
- Flight data
- Fuel data
- Aircraft position

### VATSIM API (optional)
Used for:
- Traffic
- ATC online status

### Airport data sources
- Open aviation databases
- Navdata

## Tech stack

### Frontend
- React
- Tailwind CSS
- Mapbox GL (maps)

### Backend
- Node.js
- Express API

### Database
- PostgreSQL

### Realtime data
- WebSockets

### Sim connection
- SimConnect bridge app

## Future features
- AI ATC predictor (predict clearance before contacting ATC)
- Event traffic planner (expected arrival queues during events)
- Virtual airline integration (automatic PIREP generation)
- Shared flight replay (pilots share flights and landings)

## MVP scope

### Version 1 should include
- Flight planner
- Airport intelligence
- Taxi map
- Basic live dashboard

### Skip for v1
- AI predictions
- Traffic analysis

## MVP goal
Working prototype used by pilots daily.

## Opportunity note
A major opportunity likely exists for one standout feature no one has built well yet in flight simulation. If implemented correctly, this could spread widely across the MSFS and VATSIM community.
