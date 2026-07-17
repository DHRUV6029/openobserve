# PR assets — fix for #12897 (logs Timechart)

Both recordings follow the identical flow:
login -> Logs -> select stream `e2e_timechart` -> query `match_all('error')`
-> open Timechart tab -> switch chart type to Horizontal bar -> **refresh the URL**.

## Videos (GitHub accepts .webm attachments directly)
- `before-refresh-bug.webm` — unfixed build: everything works until the refresh,
  then "Select * query is not supported for visualization" toast + permanent "No Data".
- `after-fix-full-flow.webm` — fixed build: after refresh the chart type (h-bar),
  query, and chart all restore and render. No errors.

## Screenshots
- 01/02 (before) — Timechart and h-bar render fine *before* refreshing (unfixed build)
- 03 (before) — THE BUG: state after refresh — error toast + No Data
- 04/05 (after) — same flow on the fixed build
- 06 (after) — THE FIX: state after refresh — chart type restored, chart rendered, no errors
