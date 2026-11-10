# API Route Inventory

Target: https://console.byteplus.com (account A 3000823185 unless noted)

| Method | Path | Parent Top-Level Route | Auth | Status | Summary |
|---|---|---|---|---|---|
| GET | /api/top/account_verify/ap-southeast-1/2018-01-01/GetProfileInfo | /finance/overview | test user A | completed | Returns session account only; AccountID/body ignored. |
| POST | /api/top/account_verify/ap-southeast-1/2018-01-01/GetRawProfileInfo | /finance/overview | test user A | completed | Body AccountId ignored; returns session profile. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/QueryCreditProtocolDetail | /finance/overview | test user A | completed | AccountID ignored; session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2022-01-01/ListMonthlyBillOpen | /finance/overview | test user A | completed | PayerID honored as filter; cross-account PayerID returns empty (B has bill for same period -> not readable). |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/CheckPaymentQualification | /finance/overview | test user A | completed | AccountID ignored; session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2022-01-01/GetTaxID | /finance/overview | test user A | completed | AccountID ignored; session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListEmailForAccount | /finance/overview | test user A | completed | Session-scoped email list. |
| POST | /api/top/bill/ap-singapore-1/2020-01-01/ListAccountFinancialRole | /finance/overview | test user A | completed | Session-scoped. |
| GET | /api/financial/const/getExpenseConfigForFE | /finance/overview | test user A | completed | Static config; no data. |
| GET | /api/top/bill/ap-singapore-1/2022-01-01/ListMonthlyBillOpen (bill detail) | /finance/bill/detail | test user A | completed | Same endpoint as overview; payer filter session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListSubscribeRecords | /finance/bill/detail | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/GetFilterInfoForBillDetail | /finance/bill/detail | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListPayerAndOwnerByBillOwnerID | /finance/bill/detail | test user A | completed | Returns session payer/owner. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListBcProductSummaryOpen | /finance/bill/detail | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2022-01-01/QuerySubscribeSplitBill | /finance/bill/split-bill | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/QueryAmortizedCostBillUser | /finance/bill/cost-bill | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/QuerySubscribeCostAnalysis | /finance/bill/cost-analyse | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/GetFilterInfoForCostAnalysis | /finance/bill/cost-analyse | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListCostAnalysisReport | /finance/bill/report | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2022-01-01/ListOrder | /finance/order | test user A | completed | Session-scoped order list. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2022-01-01/GetCountryAreaCfgByAccountID | /finance/order | test user A | completed | Wrong version; returns InvalidActionOrVersion. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListSubjectCodeForInstance | /finance/renew | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListRenewSettings | /finance/renew | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListInstanceForTerminate | /finance/unsubscribe | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListInstanceForConsole | /finance/instance-manage | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListInstanceConfigTimeline | /finance/instance-manage | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/BatchGetInstanceOpsCapability | /finance/instance-manage | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListResourcePackage | /finance/resource-package | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListSavingPlanConsoleAPI | /finance/saving-plan | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/GetSavingAmountSummaryConsoleAPI | /finance/saving-plan | test user A | completed | Session-scoped. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListBalanceTransactionForPage | /finance/payment/transactions | test user A | completed | Session-scoped. |
| POST | /api/top/bill/ap-singapore-1/2020-01-01/GetBalanceFromTradeBalance | /finance/payment/make-payment | test user A | completed | Session-scoped. |
| POST | /api/financial/payment/FetchStoredPaymentMethods | /finance/payment/payment-methods | test user A | completed | Session-scoped. |
| GET | /api/financial/const/getCashierTccConfig | /finance/payment/payment-methods | test user A | completed | Static config. |
| GET | /api/top/bill/ap-singapore-1/2020-01-01/ListCoupon | /finance/coupon | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListRedeemCodes | /finance/pickup-coupon | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListPickupVouchers | /finance/pickup-coupon | test user A | completed | Session-scoped. |
| GET | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListInvoiceBPV2 | /finance/invoice-manage | test user A | completed | Session-scoped invoice list. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListInvoiceMakerInfoBP | /finance/invoice-manage | test user A | completed | Session-scoped. |
| POST | /api/top/bill/ap-singapore-1/2020-01-01/GetServiceSigningRecord | /finance/busniess-finance/relation | test user A | completed | Requires ServiceType; session-scoped. |
| POST | /api/top/bill/ap-singapore-1/2020-01-01/ListFinancialRelationOnPage | /finance/busniess-finance/relation | test user A | completed | Session-scoped relations. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/QueryContractDiscountDisclaimer | /finance/contract-discount | test user A | completed | Static disclaimer. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ContractDiscountTableList | /finance/contract-discount | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/QueryContractDiscount | /finance/contract-discount | test user A | completed | Session-scoped. |
| GET | /api/top/volc_contract_process/ap-singapore-1/2021-01-01/List | /finance/contract | test user A | completed | Session-scoped contract list. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/QueryBudgetActiveInfo | /finance/cost | test user A | completed | Session-scoped. |
| POST | /api/top/bill_volcano_engine/ap-singapore-1/2020-01-01/ListBudget | /finance/cost | test user A | completed | Session-scoped. |
| POST | /api/financial/download/ListTask | /finance/export | test user A | completed | Session-scoped export tasks. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/ListTicket | /workorder/list/ | test user A+B | completed | Session-scoped; spoofed AccountID/SubmitterID ignored. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/GetTicket | /workorder/list/detail | test user A+B | completed | Cross-account TicketID -> Forbidden in both directions. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/ListTicketConversation | /workorder/list/detail | test user A+B | completed | Cross-account TicketID -> Forbidden. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/ListTicketExecutableAction | /workorder/list/detail | test user A+B | completed | Cross-account TicketID -> Forbidden. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/GetTicketCount | /workorder/list/ | test user A+B | completed | Session-scoped. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/GetTicketCountForUser | /workorder/list/ | test user A+B | completed | Session-scoped. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/GetTicketReviewTemplate | /workorder/list/detail | test user A | completed | Metadata. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/DynamicCustomFieldList | /workorder/create | test user A | completed | Form metadata. |
| POST | /api/top/ticket/ap-southeast-1/2021-01-01/ListAllFlow | /workorder/create | test user A | completed | Form metadata. |
| GET | /api/top/iam/ap-southeast-1/2018-01-01/ListUsers | /workorder/list/ | test user A | completed | Session tenant users only. |
| GET | /api/top/iam/ap-southeast-1/2018-01-01/ListRoles | /workorder/list/ | test user A | completed | Session tenant roles only. |
| POST | /api/workorder/ticket/Tcc | /workorder/create | test user A | completed | Metadata. |
| GET | /api/workorder/ticket/getWorkorderConsoleConfig | /workorder/create | test user A | completed | Config. |
| GET | /api/workorder/ticket/GetAccountMaskedSecurityContact | /workorder/create | test user A | completed | Masked session contact. |
| POST | /api/workorder/ticket/getFormTokenAndCodeList | /workorder/list/detail | test user A | completed | Form tokens. |
