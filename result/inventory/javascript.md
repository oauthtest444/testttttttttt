# JavaScript Inventory (URLs, hashes, dedupe only)

Status: scanned via exact client-side skill regexes.

- Finance app: `res.gcloudcache.com/bp-fe/finance/byteplus/static/js/1.0.1.3005/` main + async chunks; finance SDK `finance/volcf-sdk-app`.
- Workorder app: `res.gcloudcache.com/bp-fe/workorder-web/static/js/` main, WorkOrderDetail, and async chunks.
- Source/sink match counts and conclusions: see per-route reports under `result/client-side/console.byteplus.com/`.
- No downloaded bundles saved under `result/` (kept only in /tmp during analysis).

| Bundle group | Files scanned | source_get | source_url | redirect | locassign | elem | html | react |
|---|---|---|---|---|---|---|---|---|
| finance/byteplus + volcf-sdk-app | 29 | 1371 | 6 | 19 | 14 | 30 | 34 | 6 |
| workorder-web | 10 | 237 | 3 | 7 | 3 | 10 | 10 | 5 |
