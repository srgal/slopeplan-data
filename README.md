# SlopePlan open data — ski-area graphs and places

This repository publishes the **derivative database** that the SlopePlan app ships for ski routing,
as required by the Open Database License (ODbL) 1.0, §4.6. It is updated with every app build that changes the data.

| Folder | Ski area | OpenSkiData snapshot | Pistes / lifts |
|---|---|---|---|
| `flachau/` | Snow Space Salzburg (Flachau · Wagrain · St. Johann-Alpendorf) | osd-2026.10.02 | 280 / 46 |
| `mayrhofen/` | Mayrhofen (Penken · Ahorn · Horberg · Rastkogel · Eggalm) | osd-2026.10.10 | 456 / 44 |
| `ischgl/` | Silvretta Arena Ischgl / Samnaun | osd-2026.10.22 | 466 / 45 |

| File | What it is |
|---|---|
| `<area>/terrain.json` | Ski-area graph: pistes (with piste numbers), lifts, connections, routing nodes, villages |
| `<area>/pois.json` | Places near the pistes (restaurants, huts, hotels, services) |
| `flachau/osm-g-link.json` | The G-Link Wagrain lift's ride-down flag, taken from OpenStreetMap |

## Sources and attribution

- **© OpenStreetMap contributors** — https://www.openstreetmap.org/copyright — data available under the ODbL.
- **OpenSkiData** (https://openskidata.org), which is itself derived from OpenStreetMap — ODbL.

## How it was derived

1. Pistes and lifts of each ski area were taken from the OpenSkiData export (runs and lifts GeoJSON).
2. Runs and lifts were split at shared points into a directed graph. Pistes run downhill and lifts run uphill. Lift
   stations, piste ends and junctions became nodes. Elevations come from open terrain data.
3. Village bases were attached to their nearest valley nodes. Short walking connections between nearby nodes that no
   mapped way confirms are marked `verified: false` (and listed in `review`).
4. Places were taken from OpenStreetMap (Overpass API) within the ski area and linked to the nearest piste node.

Lift **status** and **operating hours** are not part of this database. The app uses published operating hours entered
by hand (with their source and date), or labelled simulated data.

## Licence

This database is made available under the **Open Database License (ODbL) 1.0**; see [LICENSE](LICENSE).
Any rights in individual contents of the database are licensed under the Database Contents License.

If you publicly use this database, a derivative of it, or a work produced from it, you must attribute
"© OpenStreetMap contributors, OpenSkiData", keep it open under the ODbL, and offer any derivative database
under the ODbL.

Generated 2026-10-29 (app data as of SlopePlan main 8ce4719, 2026-11-01).
