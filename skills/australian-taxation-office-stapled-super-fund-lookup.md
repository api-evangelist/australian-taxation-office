---
name: stapled-super-fund-lookup
description: Request a payee's stapled superannuation fund from the ATO and fetch the outcome by receipt number.
api: openapi/australian-taxation-office-stapled-super-fund-openapi.yml
operations:
- requestStapledSuperFundForPayeeWithAbn
- requestStapledSuperFundForPayeeWithReceiptNumberAndAbn
generated: '2026-10-22'
method: generated
---

# Request a payee's stapled superannuation fund from the ATO and fetch the outcome by receipt number.

Skill generated from the published ATO API Portal spec. No provider-published skills or AGENTS.md were found (https://apiportal.ato.gov.au/AGENTS.md returned 404).

1. Obtain an OAuth2 client-credentials token with scope `ato.super.stapledsuperfund.c,r` (the spec names the token URL; this skill does not call it).
2. `requestStapledSuperFundForPayeeWithAbn`: POST the request for the payee (employer identified by identifierType/identifierValue). Keep the returned receipt.
3. `requestStapledSuperFundForPayeeWithReceiptNumberAndAbn`: GET `/{receipt}` to fetch the outcome.
4. Errors documented in the spec: 400, 422, 500. Treat 422 as a data-validation failure: fix the payload, do not retry it unchanged.
5. POST is not documented as idempotent. Do not resend a request that may have succeeded; poll the receipt instead.
