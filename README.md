# Vinayaka Astro V2

Tamil-first Vedic astrology web app for generating a birth-time planetary view with South Indian charts and Dasha timelines.

## What this app does

- Computes planetary longitudes (Lagna, Sun, Moon, Mars, Mercury, Jupiter, Venus, Saturn, Rahu, Ketu) for a selected date/time and city.
- Calculates and adds **Maanti (மாந்தி)** based on sunrise/sunset and Vedic day-period rules.
- Renders **Rasi chart (ராசி)** in South Indian layout.
- Renders **Navamsa chart (நவாம்சம்)**.
- Shows sunrise/sunset and Vedic weekday period (day/night) in Tamil.
- Builds a planetary details table with house number, dignity (`ஆட்சி`, `உச்சம்`, `நீசம்`), nakshatra/pada, nakshatra lord, and retrograde marker `(வ)` where applicable.
- Generates Vimshottari Dasha data in Tamil with interactive Mahadasha, Bhukti, and Antara views.

## UI inputs

- Year: `1800` to `2200`
- Month, day, hour, minute
- Predefined city list (India + selected global cities such as London, New York, Chicago, etc.)

## Tech stack

- Plain HTML/CSS/JavaScript (no build system, no framework)
- Client-side only calculations
- SVG chart rendering

## Key files

- `index.html`  
  Main page, input controls, styling, orchestration (`calculatePositions()`).
- `js/planets.js`  
  Core astronomy/planet routines (`planets`, `ascendant`, Julian/date helpers).
- `js/astro_calc.js`  
  Planetary position shaping, Nakshatra/Pada, Navamsa calculations.
- `js/charts.js`  
  South Indian Rasi/Navamsa SVG rendering.
- `js/dignity_and_table.js`  
  Retrograde check, dignity mapping, planetary result table output.
- `js/dashas.js`  
  Vimshottari Dasha/Bhukti/Antara generation and rendering.
- `js/cities.js`  
  City coordinates, timezone metadata, Tamil city names, DST handling helpers.
- `js/sunrise.js`  
  NOAA-style sunrise/sunset calculation and Vedic weekday determination.
- `js/date_utils.js`  
  Date formatting and system Julian day utility.
- `js/panchanga.js`  
  Panchanga calculation helpers (currently present but not wired into `index.html` UI).

## Run locally

Because this is a static client-side app, you can run it directly:

1. Open `index.html` in a browser.

Recommended (to avoid browser restrictions in some environments):

1. Serve the folder with a static server, then open the served URL.

Example:

```bash
cd /Users/raviannaswamy/projects/vinayaka-astro-v2
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Notes

- Language/content is primarily Tamil.
- Calculations depend on predefined city metadata; adding new locations requires updating `js/cities.js`.
