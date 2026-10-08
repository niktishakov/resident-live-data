# Resident Live — public data

Static data the Resident Live app downloads at runtime. Served by GitHub Pages:

    https://niktishakov.github.io/resident-live-data/boundaries/v1/<ISO2>.json

## boundaries/v1

One GeoJSON `FeatureCollection` per country, keyed by ISO 3166-1 alpha-2, plus
`index.json` listing the codes. Properties: `name`, `ISO3166-1-Alpha-2`,
`ISO3166-1-Alpha-3`, `source`.

- Source: [geoBoundaries CGAZ ADM0](https://www.geoboundaries.org) — Runfola et al.,
  *geoBoundaries: A global database of political administrative boundaries*,
  PLoS ONE 15(4), 2020. Licence CC BY 4.0. Simplified to a 30 m interval.
- Territories CGAZ does not list: [Natural Earth](https://www.naturalearthdata.com)
  1:10m, public domain.

A new version of the data goes to `boundaries/v2/`, never over `v1/`: installed
apps cache what they fetched and expect a path to keep its contents.
