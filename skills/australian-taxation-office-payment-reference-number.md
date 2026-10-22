---
name: payment-reference-number
description: Retrieve a Payment Reference Number (PRN) for paying the ATO.
api: openapi/australian-taxation-office-payment-reference-number-openapi.yml
operations:
- retrievePaymentReferenceNumberFormat4
generated: '2026-10-22'
method: generated
---

# Retrieve a Payment Reference Number (PRN) for paying the ATO.

Skill generated from the published ATO API Portal spec. No provider-published skills or AGENTS.md were found (https://apiportal.ato.gov.au/AGENTS.md returned 404).

1. Authenticate with the DSG machine credentials required by the ATO API Portal.
2. `retrievePaymentReferenceNumberFormat4`: GET the PRN for the client.
3. Documented responses: 200, 400, 401, 403, 404, 500. 401/403 means the credential or the client authorisation is missing. 404 means no PRN was found.
4. This is a read-only call and is safe to retry on 500.
