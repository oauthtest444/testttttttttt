# Server-Side Report — console.byteplus.com

Target routes: `/finance/overview` (25 sub-routes), `/workorder/list/` (3 sub-routes)
Auth: account A 3000823185 and account B 3001021825 (disposable test accounts)
Status: completed (no high-impact server-side finding confirmed)

## Coverage

- Finance APIs inventoried and exercised: bill, bill_volcano_engine, account_verify, financial
  payment/config, volc_contract_process. See `result/inventory/api-routes.md`.
- Work-order APIs exercised: ListTicket, GetTicket, ListTicketConversation,
  ListTicketExecutableAction, GetTicketCount, GetTicketCountForUser.
- Bug classes attempted: IDOR/BOLA, broken access control, mass assignment/parameter
  overriding on account identifiers, PII leakage, business-logic parameter manipulation,
  cross-account reads with a second session.

## Key results

- Account identifiers are server-pinned: `GetRawProfileInfo(AccountId=B)`, `GetTaxID(AccountID=B)`,
  `QueryCreditProtocolDetail(AccountID=B)`, `CheckPaymentQualification(AccountID=B)` all return
  account A's data when called by A. No cross-account leakage.
- `ListMonthlyBillOpen` with `PayerID=B` returns empty for A while B's own session returns B's
  bill for the same period -> PayerID is filtered and authorized.
- `ListTicket` ignores spoofed `AccountID`/`SubmitterID` and returns only the caller's tickets.
- `GetTicket`, `ListTicketConversation`, `ListTicketExecutableAction` on the other account's
  ticket return `Forbidden` in both directions. No ticket IDOR.
- Stored HTML in ticket description is escaped on render; not XSS.
- Invoice lists are empty for both test accounts; cross-account filters returned no data.
- No mass-assignment change to a protected property persisted in any tested write flow.

## Unresolved / limitations

- `/finance/opening-service/:Product` was not exercised with a concrete product.
- Several write/create endpoints (budget, ticket creation, payment method add) were not invoked
  to avoid unnecessary production side effects; no evidence of a vulnerability there.
- Related `byteplus.com` subdomains remain scope-unverified and were not tested.
