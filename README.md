# SlopePlan open data — Snow Space Salzburg (Flachau)

This repository publishes the **derivative database** that the SlopePlan app ships for ski routing,
as required by the Open Database License (ODbL) 1.0, §4.6.

| File | What it is |
|---|---|
| `flachau/terrain.json` | Ski-area graph: pistes (with piste numbers), lifts, connections, routing nodes, villages |
| `flachau/pois.json` | Places near the pistes (restaurants, huts, hotels, services) |

## Sources and attribution

- **© OpenStreetMap contributors** — https://www.openstreetmap.org/copyright — data available under the ODbL.
- **OpenSkiData** (https://openskidata.org), which is itself derived from OpenStreetMap — ODbL.

## How it was derived

1. Pistes and lifts for the Snow Space Salzburg ski area were taken from the OpenSkiData export (runs and lifts GeoJSON).
2. Runs and lifts were split at shared points into a directed graph. Pistes run downhill and lifts run uphill. Lift stations, piste ends and junctions became nodes.
3. Village bases were attached to their nearest valley nodes. Short walking connections between nearby nodes are marked `verified: false`.
4. Places were taken from OpenStreetMap (Overpass API) within the ski area and linked to the nearest piste node.

Lift **status** and **operating hours** are not part of this database. The app uses published operating hours entered by hand, or labelled simulated data.

## Licence

This database is made available under the **Open Database License (ODbL) 1.0**; see [LICENSE](LICENSE).
Any rights in individual contents of the database are licensed under the Database Contents License.

If you publicly use this database, a derivative of it, or a work produced from it, you must attribute
"© OpenStreetMap contributors, OpenSkiData", keep it open under the ODbL, and offer any derivative database
under the ODbL.

Snapshot: `osd-2026.10.02` (generated 2026-10-02).
