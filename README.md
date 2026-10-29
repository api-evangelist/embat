# Embat

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Embat is a real-time treasury management platform for finance teams, founded in Madrid and backed by Creandum. Its REST/JSON API (OpenAPI 3.1, 103 operations across 21 resource areas) connects third-party applications and ERPs to Embat to manage bank connections, balances, transactions, payments and payment orders, cash-flow forecasting, scenarios, accounting entries and accounts, contacts, and bank reconciliation across multiple companies. Authentication is HTTP Bearer using a JWT idToken obtained from an email/password token endpoint (60-minute expiry, no refresh); every resource is scoped by a companyId path parameter and list endpoints paginate with limit + nextPageToken.

**Areas:** Company · Fintech · Treasury Management · Payments · Cash Flow · Banking · Reconciliation · Forecasting

## Embat on APIs.io

Everything profiled for Embat is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/embat/](https://apis.io/providers/embat/)** — or go straight to one of the APIs or properties below.

### APIs (22)

- [Embat AccountingAccounts API](https://apis.io/apis/embat/embat-accountingaccounts-api/) — `AccountingAccount` represents an account in the company's chart of accounts. `accountingCode` is the unique identifier of an account and is used as its ID;…
- [Embat Attributes API](https://apis.io/apis/embat/embat-attributes-api/) — `Attribute` represents a custom field that you can define once and then use to tag records across Embat, such as an ERP dimension, a cost center or any…
- [Embat Authentication API](https://apis.io/apis/embat/embat-authentication-api/) — `Authentication` provides the credentials Embat issues to access the rest of the public API. Every other endpoint requires a JWT `idToken` in the…
- [Embat Balances API](https://apis.io/apis/embat/embat-balances-api/) — `Balance` represents the end-of-day balance of a bank product (account) for a given calendar day. Embat records one balance per product per day, expressed…
- [Embat Banks API](https://apis.io/apis/embat/embat-banks-api/) — `Bank` represents a banking relationship connected to your company in Embat — for example, an aggregated connection to a specific banking entity. Each bank…
- [Embat Categories API](https://apis.io/apis/embat/embat-categories-api/) — `Category` represents a treasury or cashflow classification in Embat, used to group transactions, forecasts and operations for reporting (e.g. "Providers",…
- [Embat Companies API](https://apis.io/apis/embat/embat-companies-api/) — A `Company` represents a legal entity configured in your Embat workspace. Its `id` is the `companyId` used throughout this API: almost every other endpoint…
- [Embat Contacts API](https://apis.io/apis/embat/embat-contacts-api/) — `Contact` represents a client or supplier your company transacts with. `customId` is the unique identifier of a contact: set your own value to use as your…
- [Embat DebtScheduleConfigs API](https://apis.io/apis/embat/embat-debtscheduleconfigs-api/) — <div style="background-color:#fff3cd; color:#856404; padding: 10px; border-left: 6px solid #ffeeba;"> <strong>⚠️ Warning:</strong> This API section is in…
- [Embat Files API](https://apis.io/apis/embat/embat-files-api/) — `File` represents a banking file exchanged between Embat and a bank: either a file **received** from a bank (a reception, e.g. an account statement or a…
- [Embat Forecasts API](https://apis.io/apis/embat/embat-forecasts-api/) — `Forecast` represents a treasury cash flow projection generated by Embat for a given date, classified under a `Category` and grouped into a `Scenario` (e.g.…
- [Embat ForeignExchangeRates API](https://apis.io/apis/embat/embat-foreignexchangerates-api/) — `ForeignExchangeRate` records the daily exchange rates Embat uses to convert amounts between currencies for accounting purposes. Each record captures the…
- [Embat Logs API](https://apis.io/apis/embat/embat-logs-api/) — `Logs` let your integration report execution events, warnings or errors observed while interacting with the Embat API, so Embat's support team can diagnose…
- [Embat Operations API](https://apis.io/apis/embat/embat-operations-api/) — `Operation` represents an accounting operation with a pending amount to settle — typically an invoice or bill due from or to a `Contact` (client or…
- [Embat Payments API](https://apis.io/apis/embat/embat-payments-api/) — `Payment` represents money moving between a bank transaction and the operations (invoices, bills) or accounting entries it settles. `customId` is the unique…
- [Embat Products API](https://apis.io/apis/embat/embat-products-api/) — `Product` represents a bank account, credit line, card or wallet held by the company — either aggregated automatically from a bank connection, or added…
- [Embat ReconcilingItems API](https://apis.io/apis/embat/embat-reconcilingitems-api/) — <div style="background-color:#fff3cd; color:#856404; padding: 10px; border-left: 6px solid #ffeeba;"> <strong>⚠️ Warning:</strong> This API section is in…
- [Embat ReconcilingSources API](https://apis.io/apis/embat/embat-reconcilingsources-api/) — <div style="background-color:#fff3cd; color:#856404; padding: 10px; border-left: 6px solid #ffeeba;"> <strong>⚠️ Warning:</strong> This API section is in…
- [Embat Scenarios API](https://apis.io/apis/embat/embat-scenarios-api/) — A `Scenario` represents a forecasting hypothesis in Embat's treasury forecast: a named, currency-denominated projection covering a defined horizon…
- [Embat Transactions API](https://apis.io/apis/embat/embat-transactions-api/) — `Transaction` represents a movement recorded on one of your bank accounts (`Product`). Each transaction reports the balance of its product immediately after…
- [Embat Accounting Entries API](https://apis.io/apis/embat/embat-accounting-entries-api/) — `AccountingEntry` represents a single line of a company's general accounting journal — an outflow (`assetAmount`) or inflow (`liabilityAmount`) movement…
- [Embat Payment Orders API](https://apis.io/apis/embat/embat-payment-orders-api/) — ⚠️ Warning: This API section is in BETA.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [embat](https://apis.io/servers/embat/embat/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Embat Agentic Access](https://apis.io/agentic-access/embat/embat-agentic-access/)

#### Collections (22)

Postman and Open Collection request collections.

- [Embat AccountingAccounts API](https://apis.io/collections/embat/open-embat-accountingaccounts-api/)
- [Embat AccountingAccounts AccountingEntries API](https://apis.io/collections/embat/open-embat-accountingentries-api/)
- [Embat AccountingAccounts Attributes API](https://apis.io/collections/embat/open-embat-attributes-api/)
- [Embat AccountingAccounts Authentication API](https://apis.io/collections/embat/open-embat-authentication-api/)
- [Embat AccountingAccounts Balances API](https://apis.io/collections/embat/open-embat-balances-api/)
- [Embat AccountingAccounts Banks API](https://apis.io/collections/embat/open-embat-banks-api/)
- [Embat AccountingAccounts Categories API](https://apis.io/collections/embat/open-embat-categories-api/)
- [Embat AccountingAccounts Companies API](https://apis.io/collections/embat/open-embat-companies-api/)
- [Embat AccountingAccounts Contacts API](https://apis.io/collections/embat/open-embat-contacts-api/)
- [Embat AccountingAccounts DebtScheduleConfigs API](https://apis.io/collections/embat/open-embat-debtscheduleconfigs-api/)
- [Embat AccountingAccounts Files API](https://apis.io/collections/embat/open-embat-files-api/)
- [Embat AccountingAccounts Forecasts API](https://apis.io/collections/embat/open-embat-forecasts-api/)
- [Embat AccountingAccounts ForeignExchangeRates API](https://apis.io/collections/embat/open-embat-foreignexchangerates-api/)
- [Embat AccountingAccounts Logs API](https://apis.io/collections/embat/open-embat-logs-api/)
- [Embat AccountingAccounts Operations API](https://apis.io/collections/embat/open-embat-operations-api/)
- [Embat AccountingAccounts PaymentOrders API](https://apis.io/collections/embat/open-embat-paymentorders-api/)
- [Embat AccountingAccounts Payments API](https://apis.io/collections/embat/open-embat-payments-api/)
- [Embat AccountingAccounts Products API](https://apis.io/collections/embat/open-embat-products-api/)
- [Embat AccountingAccounts ReconcilingItems API](https://apis.io/collections/embat/open-embat-reconcilingitems-api/)
- [Embat AccountingAccounts ReconcilingSources API](https://apis.io/collections/embat/open-embat-reconcilingsources-api/)
- [Embat AccountingAccounts Scenarios API](https://apis.io/collections/embat/open-embat-scenarios-api/)
- [Embat AccountingAccounts Transactions API](https://apis.io/collections/embat/open-embat-transactions-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Embat Openapi Overlay](https://apis.io/overlays/embat/embat-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Embat Authentication](https://apis.io/security/embat/embat-authentication/)
- [Embat Domain Security](https://apis.io/security/embat/embat-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.embat.io/)
- [Documentation](https://api.embat.io/docs)
- [API reference](https://api.embat.io/docs)

## API Evangelist rating

**Kin Score 28.7** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 50.7 |
| Contract governance | 4.5 |
| Operational transparency | 0.0 |
| Developer ergonomics | 37.5 |
| Access clarity | 6.6 |

**Agent readiness 29.0** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 13.4** — Banking & Open Finance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/embat/](https://apis.io/providers/embat/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Embat: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/embat/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
