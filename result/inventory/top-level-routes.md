# Top-Level Route Inventory

Target: https://console.byteplus.com

| Top-Level Route | Status | Sub-Routes | Summary |
|---|---|---|---|
| https://console.byteplus.com/finance/overview | completed | 25 | Finance center sub-routes, APIs, and shared JS tested; no high-impact finding. |
| https://console.byteplus.com/workorder/list/ | completed | 3 | Ticket list/detail/create APIs and JS tested; cross-account access blocked. |

## https://console.byteplus.com/finance/overview

Status: completed

| Sub-Route | Status | Summary |
|---|---|---|
| /finance/overview | completed | APIs session-pinned; client JS scanned. |
| /finance/bill/detail | completed | Bill queries session-pinned. |
| /finance/bill/tag | completed | No data-bearing API on load. |
| /finance/bill/split-bill | completed | Session-scoped. |
| /finance/bill/cost-bill | completed | Session-scoped. |
| /finance/bill/cost-analyse | completed | Session-scoped. |
| /finance/bill/report | completed | Session-scoped. |
| /finance/order | completed | Account params pinned. |
| /finance/renew | completed | Session-scoped. |
| /finance/unsubscribe | completed | Session-scoped. |
| /finance/instance-manage | completed | Session-scoped. |
| /finance/resource-package | completed | Session-scoped. |
| /finance/saving-plan | completed | Session-scoped. |
| /finance/opening-service/:Product | completed | Parameterized; not exercised with a product (documented unresolved). |
| /finance/payment/transactions | completed | Session-scoped. |
| /finance/payment/make-payment | completed | Session-scoped. |
| /finance/payment/payment-methods | completed | Session-scoped. |
| /finance/coupon | completed | Session-scoped. |
| /finance/pickup-coupon | completed | Session-scoped. |
| /finance/invoice-manage | completed | Session-scoped; both accounts had zero invoices. |
| /finance/busniess-finance/relation | completed | Session-scoped. |
| /finance/contract-discount | completed | Session-scoped. |
| /finance/contract | completed | Session-scoped. |
| /finance/cost | completed | Session-scoped. |
| /finance/export | completed | Session-scoped tasks. |

## https://console.byteplus.com/workorder/list/

Status: completed

| Sub-Route | Status | Summary |
|---|---|---|
| /workorder/list/ | completed | ListTicket session-scoped; spoofed AccountID ignored. |
| /workorder/list/detail?id=... | completed | GetTicket/conversation/action cross-account -> Forbidden. |
| /workorder/create | completed | Read-only form metadata APIs; no ticket created. |
