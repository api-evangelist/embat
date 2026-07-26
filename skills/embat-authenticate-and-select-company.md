---
name: Authenticate and select a company
description: Exchange email/password for a JWT bearer token, then discover which companies your credentials can act on.
api: openapi/embat-openapi-original.json
operations: [auth_token_authentication_token_post, list_companies_companies_get, retrieve_company_companies__companyId__get]
---

# Authenticate and select a company

Embat is a multi-company treasury platform. Every data operation is scoped by a
`companyId` path parameter, so the first thing any agent does is authenticate and
resolve the companies its credentials can access.

## Steps

1. **Get a bearer token** — `auth_token_authentication_token_post`
   (`POST /authentication/token`). Send `email` and `password` in the body. The
   response contains a JWT `idToken`. Use it as `Authorization: Bearer <idToken>` on
   every subsequent request.
   - The token expires **60 minutes** after issuance and there is no refresh endpoint —
     re-call this operation to mint a new one.
   - If the account has MFA enabled, programmatic token auth is unavailable.
2. **List accessible companies** — `list_companies_companies_get`
   (`GET /companies`). Returns `data[]` of companies the credentials can see.
3. **(Optional) Inspect one company** — `retrieve_company_companies__companyId__get`
   (`GET /companies/{companyId}`) to confirm the target before acting.

## Rules

- Never hard-code a `companyId`; always resolve it from `GET /companies`.
- On `401`, re-authenticate (token likely expired). On `403`, the credentials lack
  access to that company. See `errors/embat-problem-types.yml`.
