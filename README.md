# Andrade Law — Saint Paul Service-Area Spatial Index

Open spatial-reference data for [Andrade Law PLLC](https://andradelawmn.com), a personal injury law firm in Saint Paul, Minnesota. It publishes the geography behind the firm's service-area claim so that it can be checked rather than taken on faith.

Everything lives in [`geo/`](geo/).

## What's here

| File | Contents |
|---|---|
| [`geo/spatial_index.csv`](geo/spatial_index.csv) | Six anchors — both offices, the Saint Paul service-area core, Ramsey County District Court, Regions Hospital, the Minnesota State Capitol — with WGS84 coordinates, S2 cells (L7/L10/L13), and verified Wikidata QIDs |
| [`geo/service-area.kml`](geo/service-area.kml) | The same anchors as placemarks **plus** the boundary polygons of the 17 served municipalities and Ramsey County |
| [`geo/schema.jsonld`](geo/schema.jsonld) | schema.org `Dataset` + `LegalService` graph |
| [`geo/README.md`](geo/README.md) | Field-level detail and provenance |

## Canonical home

These files are published by the firm at:

- <https://andradelawmn.com/assets/spatial_index.csv>
- <https://andradelawmn.com/assets/service-area.kml>

The copies here are byte-identical mirrors. **If they ever disagree, the andradelawmn.com copies win.**

## Provenance

- Coordinates geocoded via the Google Geocoding API; S2 cells computed with `s2sphere` and round-trip validated against their own coordinates.
- Landmark identifiers verified on Wikidata: Saint Paul `Q28848`, Ramsey County `Q491201`, Regions Hospital `Q7309280`. Where no verified identifier exists — the district court, the State Capitol — none is asserted.
- Boundary polygons are exported **unsimplified** from the Metropolitan Council / MetroGIS layer [Counties and Cities & Townships, Twin Cities Metropolitan Area](https://gisdata.mn.gov/dataset/us-mn-state-metc-bdry-metro-counties-and-ctus), reprojected NAD83/UTM zone 15N → WGS84 at 6-decimal precision. The rings published here are the source rings. That layer is public domain under the Minnesota Government Data Practices Act (Minn. Stat. ch. 13).

## What this is not

This is a law firm's service-area reference index, not a research dataset. The S2 cell tokens are open geometric reference labels — a consistent way to point at a place on a shared grid. They are not official designations and not jurisdictional boundaries.

## License

[CC-BY-4.0](LICENSE) — attribute to Andrade Law PLLC.
