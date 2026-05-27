# Namibia Administrative Divisions / Namibia



## Overview

| Item | Details |
|------|---------|
| Region | 14 |
| Constituency | 107 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/na](https://openadmindata.org/na/) |
| API | [openadmindata.org/api/na](https://openadmindata.org/api/na/) |

## Browse by Region

| # | Region | Constituencys | Link |
|---|----|----|------|
| 1 | Erongo | 7 | [Browse](divisions/erongo-na02/) |
| 2 | Hardap | 6 | [Browse](divisions/hardap-na03/) |
| 3 | Karas | 6 | [Browse](divisions/karas-na04/) |
| 4 | Kavango East | 6 | [Browse](divisions/kavango-east-na05/) |
| 5 | Kavango West | 3 | [Browse](divisions/kavango-west-na14/) |
| 6 | Khomas | 10 | [Browse](divisions/khomas-na06/) |
| 7 | Kunene | 6 | [Browse](divisions/kunene-na07/) |
| 8 | Ohangwena | 11 | [Browse](divisions/ohangwena-na08/) |
| 9 | Omaheke | 7 | [Browse](divisions/omaheke-na09/) |
| 10 | Omusati | 12 | [Browse](divisions/omusati-na10/) |
| 11 | Oshana | 10 | [Browse](divisions/oshana-na11/) |
| 12 | Oshikoto | 10 | [Browse](divisions/oshikoto-na12/) |
| 13 | Otjozondjupa | 7 | [Browse](divisions/otjozondjupa-na13/) |
| 14 | Zambezi | 6 | [Browse](divisions/zambezi-na01/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 14 region records |
| [all-constituency.json](data/all-constituency.json) | JSON | All 107 constituency records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['constituency']} constituencys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=constituency |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
```

Constituencys are listed inline in each region's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Namibia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/namibia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
