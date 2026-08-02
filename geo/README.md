# Saint Paul Service-Area Spatial Index — Andrade Law PLLC

Open spatial-reference data for [Andrade Law PLLC](https://andradelawmn.com), a personal-injury law firm in Saint Paul, Minnesota. It maps the firm's office and its Saint Paul service-area landmarks to **S2 Geometry** cells and WGS84 coordinates.

S2 cells are an open geometric indexing system, used here as geographic reference labels — **not** an official or administrative identifier.

## Files
- **`spatial_index.csv`** — office, Saint Paul core, Ramsey County District Court, Regions Hospital, State Capitol, and the Maplewood branch — with coordinates, S2 cells (L7/L10/L13), and verified Wikidata QIDs.
- **`service-area.kml`** — the same six anchors as placemarks for Google Earth / Maps, each carrying its S2 cells and verified Wikidata QID in `ExtendedData`, **plus the boundary polygons of the 17 served municipalities and Ramsey County**.
- **`schema.jsonld`** — schema.org `Dataset` + `LegalService` graph.

## Provenance
- Andrade Law PLLC, 1327 County Rd D Cir, Saint Paul, MN 55109 — <https://andradelawmn.com>
- Google Maps CID `103159562730421070`
- Coordinates geocoded via Google Geocoding; S2 cells computed with `s2sphere` (round-trip validated); landmark IDs verified on Wikidata (Saint Paul `Q28848`, Ramsey County `Q491201`, Regions Hospital `Q7309280`).
- **Boundary polygons:** [Counties and Cities & Townships, Twin Cities Metropolitan Area](https://gisdata.mn.gov/dataset/us-mn-state-metc-bdry-metro-counties-and-ctus) — Metropolitan Council / MetroGIS, assembled from county linework. Public domain under the Minnesota Government Data Practices Act (Minn. Stat. ch. 13). Exported through GDAL/OGR (QGIS) with **no simplification**, reprojected NAD83/UTM15N → WGS84 at 6-decimal precision. The rings here are the source rings.

## License
**CC-BY-4.0** — attribute to Andrade Law PLLC.
