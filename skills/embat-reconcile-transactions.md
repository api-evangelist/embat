---
name: Reconcile bank transactions
description: Match unreconciled bank transactions to reconciling items so the ledger stays clean.
api: openapi/embat-openapi-original.json
operations: [list_transactions_transactions__companyId__get, list_operations_reconcilingitems__companyId__get, create_reconciling_item_reconcilingitems__companyId__post]
---

# Reconcile bank transactions

Embat's reconciliation surface matches bank transactions against expected items. This
skill finds unreconciled transactions and records reconciling items.

## Steps

1. **Authenticate** and resolve `companyId`.
2. **Find unreconciled transactions** —
   `list_transactions_transactions__companyId__get`
   (`GET /transactions/{companyId}`) with `reconciled=false` and a date range.
3. **List existing reconciling items** —
   `list_operations_reconcilingitems__companyId__get`
   (`GET /reconcilingitems/{companyId}`) to see what is already staged.
4. **Create a reconciling item** —
   `create_reconciling_item_reconcilingitems__companyId__post`
   (`POST /reconcilingitems/{companyId}`) to link a transaction to its expected
   counterpart. Bulk creation is available at `POST /reconcilingitems/{companyId}/bulk`.

## Rules

- Paginate transactions with `limit` + `nextPageToken`.
- Reconciling items belong to a `reconcilingSource`; ensure the source exists
  (`GET /reconcilingsources/{companyId}`) before linking.
- Writes here are `acting`/`write`; audit is recommended (see `agentic-access/`).
