# /finance/pickup-coupon

Status: completed

- Source regex match count: 1371 (shared finance bundle: finance/byteplus 1.0.1.3005 + volcf-sdk-app)
- Sink regex match count: redirect=19, location-assign=14, element-create=30, html/eval=34, dangerouslySetInnerHTML=6
- Matched sources: `.get(`/URLSearchParams reads in router and data-table helpers (no attacker-controlled value reaching a sink)
- Matched sinks: router `location.assign/replace`, `location.href=` transitions to static app routes; `innerHTML`/`dangerouslySetInnerHTML` in vendor components with non-attacker data
- Interesting relationships: none proven; route params are consumed by the API layer, not DOM sinks
- Potential real vulnerability: none confirmed
- Evidence: API calls are JSON-only; no user-controlled source reached an execution sink
- Limitation: shared bundle scanned; per-route lazy chunks not exhaustively traced
