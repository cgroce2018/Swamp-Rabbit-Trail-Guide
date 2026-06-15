# Swamp Rabbit Trail Guide

A mobile-friendly, interactive map guide to the Prisma Health Swamp Rabbit Trail in
Greenville County, SC — trail sections by color line, points of interest within 2 miles
of where you tap, along-trail routing, current closures, and the Mauldin/Simpsonville/
Fountain Inn (Golden Strip) and Conestee (Lake Conestee Nature Trail) segments.

## Tech
- Single static page — [`index.html`](index.html) + embedded data in [`data.js`](data.js).
- [Leaflet](https://leafletjs.com/) for the map; [MapTiler](https://maptiler.com/) basemap tiles.
- Trail/POI geometry from [OpenStreetMap](https://www.openstreetmap.org/).

## Run locally
Any static server works, e.g.:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Configuration
Set your MapTiler key in `index.html` (`const TILE_KEY = '…'`) and restrict it to your
domain in the MapTiler dashboard. If left blank, the map falls back to keyless tiles.

## Data
`trail.geojson` is the source trail geometry; `data.js` is the version the page loads
(trail + points of interest + closures).
