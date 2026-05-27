# Chamber HALT Dashboard Web App

Open `index.html` in a browser and use **Upload HALT Result Spreadsheet** to
load an Excel workbook. The landing screen shows only the upload prompt; the
dashboard is displayed after the workbook is successfully loaded.

## Supported workbook layout

- Test data sheet: `Test format` (capitalization is flexible).
- Required test headings: `Meter type/Casing` and `Sample Quantity`.
- Recognized fields include `S.n`, `Meter Rating`, `Firmware ver.`, `Module
  Type`, `Network Operator`, `Start Date`, `Test Duration`, `Bugs Finding`,
  and `Fail/Total`.
- Optional bug lookup sheet: `Bug Type`, containing `Bug ID` and `Bug type`.
- Detail-result sheets after `Bug Type` are matched to their summary run using
  firmware/version or test-purpose text. Their current meter metadata and
  explicit issue evidence (`NOT OK`, failure/bug wording, or observations)
  are synchronized into the `Test format` summary used by the dashboard.

The meter type buttons (`All Types`, `1Ph CL`, and `1Ph KR`) and duration
buttons (`All Durations` plus each uploaded test duration) filter imported
rows together and refresh all KPI cards, the table, and bug summaries.
The KPI visual analysis area contains animated donut and bar charts for
pass/failure outcomes, meter-type distribution, failed/tested meters by
duration, and samples by meter type. The duration bars display `failed/total`
above each bar, with the red area showing failures within all tested meters.
Hover chart slices or bars to highlight their values.

Use **Download Synced Workbook** after upload to download a workbook whose
`Test format` sheet includes the synchronized detail-sheet values.

## Files

- `index.html`: standalone dashboard application.
- `xlsx.full.min.js`: local SheetJS parser used to read `.xls` and `.xlsx`
  files in the browser.
