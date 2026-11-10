# Session Compaction

Last updated: 2026-11-10T14:20:00Z
Current target: `https://console.byteplus.com` — routes `/finance/overview` and `/workorder/list/`
Target hash: `851361f8840b1efe993289fa5efa40d815c25b00e22682335fd394ab32253ba7`
Run: 42831571613 (schedule), event 2026-11-10T14:11:56Z, decision=preserved
Status: completed (SCAN_COMPLETE written)

## Authentication (this run)

- Account A (owner/payer): AccountID 3000823185 (`test-user-123`), logged in OK.
- Account B (second test account): AccountID 3001021825 (`testt456`), logged in OK in an
  isolated browser context.
- Cached cookies/CSRF live only in `creds/auth-headers.txt` (gitignored). No secrets copied here.
- Both sessions used for cross-account IDOR/BOLA checks on finance and ticket APIs.

## Discovered surface

- Finance sub-routes (25): overview; bill/detail, bill/tag, bill/split-bill, bill/cost-bill,
  bill/cost-analyse, bill/report; order; renew; unsubscribe; instance-manage; resource-package;
  saving-plan; opening-service/:Product; payment/transactions, payment/make-payment,
  payment/payment-methods; coupon; pickup-coupon; invoice-manage; busniess-finance/relation;
  contract-discount; contract; cost; export.
- Work-order sub-routes (3): `/workorder/list/`, `/workorder/list/detail?id=...`, `/workorder/create`.
- Ticket APIs: ListTicket, GetTicket, ListTicketConversation, ListTicketExecutableAction,
  GetTicketCount, GetTicketCountForUser, GetTicketReviewTemplate, DynamicCustomFieldList,
  ListAllFlow, plus `/api/workorder/ticket/{Tcc,getWorkorderConsoleConfig,GetAccountMaskedSecurityContact,getFormTokenAndCodeList}`.
- Finance APIs: `/api/top/bill/*`, `/api/top/bill_volcano_engine/*`, `/api/financial/*`,
  `/api/top/volc_contract_process/*`, `/api/top/account_verify/*` (inventoried in
  `result/inventory/api-routes.md`).

## Tested (evidence / result)

- Account-scoped finance params are pinned to the session, not client-controlled:
  `QueryCreditProtocolDetail`, `CheckPaymentQualification`, `GetTaxID`, `GetRawProfileInfo`
  ignore supplied AccountID and return the caller's account; `ListMonthlyBillOpen` PayerID is
  filtered/authorized (A with payer 3001021825 -> empty while B's own query returns its bill).
  => No IDOR.
- Invoice: both accounts have zero invoices; cross-account PayerID/AccountID returns empty. Inconclusive but no exposure.
- Ticket IDOR: A->B and B->A `GetTicket`, `ListTicketConversation`, `ListTicketExecutableAction`
  all return `Forbidden`; `ListTicket` ignores spoofed AccountID/SubmitterID and returns only
  the session account's tickets. => No cross-account ticket access.
- Stored HTML in ticket description (ticket I-2026103118200002) renders escaped:
  DOM has no `#agentx`/`#agentlink` and raw text is `&lt;b ...&gt;`. => Not XSS.
- Client-side: exact skill regexes run over finance (finance/byteplus 1.0.1.3005 + volcf-sdk-app)
  and workorder-web bundles. Counts: finance source_get=1371, source_url=6, redirect=19,
  locassign=14, elem=30, html=34, react=6; workorder source_get=237, source_url=3, redirect=7,
  locassign=3, elem=10, html=10, react=5. Matches are router/library/static-safe; no confirmed
  attacker source -> dangerous sink flow, no postMessage impact proven.
- No confirmed high-impact vulnerability this run. Existing server-side test tickets from prior
  runs are test-owned only.

## Pending / next

- No required work remains for this target's two supplied routes.
- `opening-service/:Product` is parameterized and was not exercised with a concrete product.
- Related `byteplus.com` subdomains remain scope-unverified unless covered by the private BBP;
  verify before testing.
- Deep client-side tracing of every lazy finance/asynchronous chunk per sub-route was not
  exhaustive; shared bundles were scanned and no source->sink flow was confirmed.

## Scope decisions

- Authorized: `console.byteplus.com` (`/finance/*`, `/workorder/*`) under the private BBP.
- Other `byteplus.com` subdomains: scope-unverified (not auto out-of-scope); recorded, not tested.
- No destructive actions, no real-user data, no ticket creation this run.

## Historical (completed prior target 2026-11-01)

Prior target routes `/datarangers`, `/datatester`, `/ark`, `/ai`, `/alb` completed 2026-11-01.
Confirmed low-impact read-only cross-project IDOR `VULN-20261031-001` in DataFinder
`common_settings` (presentation settings only, below notification bar). No high-impact findings.

## Workflow closeout

- timestamp: 2026-11-10T14:20:14Z
- run_id: 42831571613
- event: schedule
- agent_outcome: success
- workflow_status: success
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-10T14:21:12Z
- run_id: 42832159405
- event: workflow_dispatch
- agent_outcome: success
- workflow_status: success
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-10T22:46:28Z
- run_id: 42917369458
- event: schedule
- agent_outcome: success
- workflow_status: success
- note: Agent-created compaction is authoritative; this closeout records how the run ended.
