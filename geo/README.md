# Saint Paul Service-Area Spatial Index — Andrade Law PLLC

Open spatial-reference data for [Andrade Law PLLC](https://andradelawmn.com), a personal-injury law firm in Saint Paul, Minnesota. It maps the firm's office and its Saint Paul service-area landmarks to **S2 Geometry** cells and WGS84 coordinates.

S2 cells are an open geometric indexing system, used here as geographic reference labels — **not** an official or administrative identifier.

## Files

> **Canonical home:** these files are published by Andrade Law at <https://andradelawmn.com/assets/spatial_index.csv> and <https://andradelawmn.com/assets/service-area.kml>. The copies here are byte-identical mirrors — if they ever disagree, the andradelawmn.com copies win.

- **`spatial_index.csv`** — 22 nodes: both offices, the Saint Paul core, Ramsey County (document-level area), and eighteen landmarks from the firm's published points-of-interest guides — courts and the State Capitol, five hospitals and clinics, police records counters in three cities, a city hall, the impound lot, the downtown arena, and two post-crash vehicle stops — with coordinates, S2 cells (L7/L10/L13), verified Wikidata QIDs where one exists, and `photo_url`/`branded_photo_url` links to the firm's real photographs where published. One landmark (Regency Hospital, Golden Valley) lies outside the service boundary. The photo URLs point at images hosted by the firm; the images themselves are © Andrade Law PLLC and are **not** part of this CC-BY dataset.
- **`service-area.kml`** — the 13 coordinate-bearing nodes as placemarks for Google Earth / Maps, each carrying its S2 cells and verified Wikidata QID in `ExtendedData`, **plus the boundary polygons of the 17 served municipalities and Ramsey County**.
- **`schema.jsonld`** — schema.org `Dataset` + `LegalService` graph.

## Provenance
- Andrade Law PLLC, 1327 County Rd D Cir, Saint Paul, MN 55109 — <https://andradelawmn.com>
- Google Maps CID `103159562730421070`
- Coordinates geocoded via Google Geocoding; S2 cells computed with `s2sphere` (round-trip validated); landmark IDs verified on Wikidata (Saint Paul `Q28848`, Ramsey County `Q491201`, Regions Hospital `Q7309280`, Xcel Energy Center `Q1421388` — venue since renamed Grand Casino Arena). Where no verified identifier exists, none is asserted.
- **Boundary polygons:** [Counties and Cities & Townships, Twin Cities Metropolitan Area](https://gisdata.mn.gov/dataset/us-mn-state-metc-bdry-metro-counties-and-ctus) — Metropolitan Council / MetroGIS, assembled from county linework. Public domain under the Minnesota Government Data Practices Act (Minn. Stat. ch. 13). Exported through GDAL/OGR (QGIS) with **no simplification**, reprojected NAD83/UTM15N → WGS84 at 6-decimal precision. The rings here are the source rings.

## License
**CC-BY-4.0** — attribute to Andrade Law PLLC.
