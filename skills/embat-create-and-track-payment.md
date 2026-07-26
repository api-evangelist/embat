---
name: Create and track a payment
description: Register a payment for a company, then follow it through to its payment order and receipt.
api: openapi/embat-openapi-original.json
operations: [create_payment_payments__companyId__post, list_payments_payments__companyId__get, retrieve_payment_payments__companyId___customId__get, list_payment_orders_paymentorders__companyId__get]
---

# Create and track a payment

Embat lets finance teams initiate and monitor payments across their connected banks.
This is a **money-movement** flow — treat writes as high-consequence.

## Steps

1. **Authenticate** and resolve `companyId`.
2. **Create the payment** — `create_payment_payments__companyId__post`
   (`POST /payments/{companyId}`). Supply the payment body (amount, currency,
   beneficiary/contact, value date). You may assign a client-owned `customId`.
3. **List payments to confirm** — `list_payments_payments__companyId__get`
   (`GET /payments/{companyId}`). Filter by `status`, date bounds, or
   `beneficiaryLegalNameContains`.
4. **Retrieve one payment** — `retrieve_payment_payments__companyId___customId__get`
   (`GET /payments/{companyId}/{customId}`) to read its current status.
5. **Follow the payment order** — `list_payment_orders_paymentorders__companyId__get`
   (`GET /paymentorders/{companyId}`); a receipt can be downloaded from
   `GET /paymentorders/{id}/receipt`.

## Rules

- There is **no Idempotency-Key** mechanism — do not blindly retry a `POST /payments`
  that may have succeeded; confirm via list/retrieve first (see
  `conventions/embat-conventions.yml`).
- Payment creation is classified `acting`/`physical` in `agentic-access/`; require
  human confirmation for high-value or abnormal payments.
- Validation problems return `422` with a `detail[]` of `{loc, msg, type}`; fix per the
  reported location. See `errors/embat-problem-types.yml`.
