# Resident Live — public data

Static data the Resident Live app downloads at runtime. Served by GitHub Pages:

    https://niktishakov.github.io/resident-live-data/boundaries/v1/lo/<ISO2>.json

## boundaries/v1

Two levels of detail per country, keyed by ISO 3166-1 alpha-2:

- `lo/<ISO2>.json` — the whole country at a 1 km interval, for when it fits on
  screen. Its feature's properties list the close-up cells: `tileSize` (degrees)
  and `tiles` (`[x, y]`, the cell's south-west corner divided by `tileSize`).
- `hi/<ISO2>/<x>_<y>.json` — one cell at a 30 m interval, clipped to the cell's
  square. The clip adds edges along the cell's sides that are not a border.

`index.json` lists the countries. Properties: `name`, `ISO3166-1-Alpha-2`,
`ISO3166-1-Alpha-3`.

- Source: [geoBoundaries CGAZ ADM0](https://www.geoboundaries.org) — Runfola et al.,
  *geoBoundaries: A global database of political administrative boundaries*,
  PLoS ONE 15(4), 2020. Licence CC BY 4.0. Simplified to a 30 m interval.
- Territories CGAZ does not list: [Natural Earth](https://www.naturalearthdata.com)
  1:10m, public domain.

A new version of the data goes to `boundaries/v2/`, never over `v1/`: installed
apps cache what they fetched and expect a path to keep its contents.
