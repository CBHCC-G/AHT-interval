# AHT Interval Viewer (Beacon Call Center)

This lightweight web page is used by the **Beacon Call Center** (Carelon Global Solutions) to **view AHT (Average Handle Time) hourly** from uploaded CSV files. It displays the data in searchable, sortable tables and highlights rows where AHT exceeds the configured threshold.

## What this site does
- Upload one or more **CSV files** and view them in a browser
- Provides:
  - Search/filter
  - Column sorting
  - Pagination
  - Horizontal scrolling for wide reports
- Highlights rows where the AHT value is above a threshold (default: **490**)

## CSV Requirements
- Files must be valid `.csv` files
- The first row must be the **header row**
- All files must include the same AHT column header used for highlighting (configured as `HIGHLIGHT_COLUMN_NAME` in the HTML)

> Filenames must match the names configured in `TAB_CONFIG` (case-insensitive match).

## Highlight Rule (Threshold)
Rows are highlighted when:

- **Column:** `HIGHLIGHT_COLUMN_NAME` (example: `AHT`)
- **Condition:** value **> 490** (default)

You can change these values in the HTML:
- `const HIGHLIGHT_COLUMN_NAME = "AHT";`
- `const THRESHOLD = 490;`

## Customization
### Add a new tab / LOB
Edit `TAB_CONFIG` in the HTML:

```js
const TAB_CONFIG = [
  { tab: "Beacon CC", files: ["cbhccoverallAHT.csv", "cbhcc.csv"] },
  { tab: "CPCS",      files: ["cpcs.csv"] },
  { tab: "New LOB",   files: ["newlob.csv"] }
];
