# Andrade Law — Saint Paul Service-Area Spatial Index

Open spatial-reference data for [Andrade Law PLLC](https://andradelawmn.com), a personal injury law firm in Saint Paul, Minnesota. It publishes the geography behind the firm's service-area claim so that it can be checked rather than taken on faith.

Everything lives in [`geo/`](geo/).

## What's here

| File | Contents |
|---|---|
| [`geo/spatial_index.csv`](geo/spatial_index.csv) | 14 nodes — both offices, the Saint Paul service-area core, Ramsey County, and ten landmarks (the district court, Regions Hospital, the State Capitol, and seven from the firm's points-of-interest guides) — with WGS84 coordinates, S2 cells (L7/L10/L13), and verified Wikidata QIDs where one exists |
| [`geo/service-area.kml`](geo/service-area.kml) | The 13 coordinate-bearing nodes as placemarks **plus** the boundary polygons of the 17 served municipalities and Ramsey County |
| [`geo/schema.jsonld`](geo/schema.jsonld) | schema.org `Dataset` + `LegalService` graph |
| [`geo/README.md`](geo/README.md) | Field-level detail and provenance |

## Canonical home

These files are published by the firm at:

- <https://andradelawmn.com/assets/spatial_index.csv>
- <https://andradelawmn.com/assets/service-area.kml>

The copies here are byte-identical mirrors. **If they ever disagree, the andradelawmn.com copies win.**

## Provenance

- Coordinates geocoded via the Google Geocoding API; S2 cells computed with `s2sphere` and round-trip validated against their own coordinates.
- Landmark identifiers verified on Wikidata: Saint Paul `Q28848`, Ramsey County `Q491201`, Regions Hospital `Q7309280`, Xcel Energy Center `Q1421388` (venue since renamed Grand Casino Arena). Where no verified identifier exists — the district court, the State Capitol, most point-of-interest landmarks — none is asserted.
- Boundary polygons are exported **unsimplified** from the Metropolitan Council / MetroGIS layer [Counties and Cities & Townships, Twin Cities Metropolitan Area](https://gisdata.mn.gov/dataset/us-mn-state-metc-bdry-metro-counties-and-ctus), reprojected NAD83/UTM zone 15N → WGS84 at 6-decimal precision. The rings published here are the source rings. That layer is public domain under the Minnesota Government Data Practices Act (Minn. Stat. ch. 13).

## Everything here is checkable

That is the point of publishing it. Each coordinate round-trips against its published S2 cell; the boundary rings are the source rings rather than a simplification; and every asserted identifier resolves to a public authority record. Where no verified identifier exists — the district court, the State Capitol, most point-of-interest landmarks — none is asserted.

A note on the S2 tokens: they are open geometric reference labels, a consistent way to point at a place on a shared grid. They are not official designations and not jurisdictional boundaries.

## License

[CC-BY-4.0](LICENSE) — attribute to Andrade Law PLLC.
