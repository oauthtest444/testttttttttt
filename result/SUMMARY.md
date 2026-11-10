# Scan Summary — console.byteplus.com

- Scan time: 2026-11-10T14:20:04Z
- Authorization: private BBP; data/targets.txt routes `/finance/overview` and `/workorder/list/`.
- Test accounts: A 3000823185 (test-user-123), B 3001021825 (testt456); both authenticated in isolated contexts.

## Coverage

- Top-level routes: 2/2 completed.
- Finance sub-routes: 25 recorded and tested (server-side + shared client bundle).
- Work-order sub-routes: 3 (list, detail, create) tested.
- API routes inventoried: 63, all completed.
- Subdomains: console.byteplus.com completed; signin.byteplus.com scope-unverified; asset CDN out of scope.

## Findings

- Confirmed high-impact findings: none.
- Negative/defensive results:
  - Account-scoped finance parameters (AccountID/PayerID) are session-pinned; cross-account values return the caller's data or empty.
  - Ticket detail/conversation/action APIs return Forbidden for the other test account; ticket list ignores spoofed AccountID/SubmitterID.
  - Stored HTML in ticket description renders escaped (no XSS).
  - Client-side regex scan found only router/library/static sink usage; no confirmed source→sink flow.

## Unresolved / limitations

- `/finance/opening-service/:Product` not exercised with a concrete product.
- No ticket/budget/payment-method creation performed (avoided production side effects).
- Related `byteplus.com` subdomains remain scope-unverified.

## Evidence and reports

- `result/server-side/console.byteplus.com/route-report.md`
- `result/client-side/console.byteplus.com/<route>/route-report.md`
- Inventories under `result/inventory/`; continuity in `result/SESSION_COMPACTION.md`.
