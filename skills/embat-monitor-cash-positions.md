---
name: Monitor bank balances and cash positions
description: Pull a company's connected banks, current balances, and transaction feed to report real-time cash position.
api: openapi/embat-openapi-original.json
operations: [list_banks_banks__companyId__get, list_balances_balances__companyId__get, list_transactions_transactions__companyId__get]
---

# Monitor bank balances and cash positions

Embat aggregates bank connections so finance teams see a real-time consolidated cash
position. This skill reads that surface (read-only).

## Steps

1. **Authenticate** and resolve `companyId` (see
   `embat-authenticate-and-select-company.md`).
2. **List connected banks** — `list_banks_banks__companyId__get`
   (`GET /banks/{companyId}`).
3. **List balances** — `list_balances_balances__companyId__get`
   (`GET /balances/{companyId}`). Filter with `baseCurrency` and date bounds
   (`startDate`/`endDate`) as needed.
4. **List transactions** — `list_transactions_transactions__companyId__get`
   (`GET /transactions/{companyId}`). Use `startDate`/`endDate`, `reconciled`,
   `productId` filters to scope the feed.

## Rules

- Responses paginate with `limit` + `nextPageToken`; keep passing the returned
  `nextPageToken` until it is absent to read the full feed. See
  `conventions/embat-conventions.yml`.
- These are read operations (`connected`/`read` in `agentic-access/`); safe for
  low-friction agent access.
