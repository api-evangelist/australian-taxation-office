---
name: global-domestic-minimum-tax-return
description: Lodge or amend a Combined Global and Domestic Minimum Tax return, plus group-entity returns.
api: openapi/australian-taxation-office-global-domestic-minimum-tax-return-openapi.yml
operations:
- requestGlobalDomesticMinimumTaxReturnFormABN
- requestGlobalDomesticGroupEntityTaxReturnForm
generated: '2026-10-22'
method: generated
---

# Lodge or amend a Combined Global and Domestic Minimum Tax return, plus group-entity returns.

Skill generated from the published ATO API Portal spec. No provider-published skills or AGENTS.md were found (https://apiportal.ato.gov.au/AGENTS.md returned 404).

1. `requestGlobalDomesticMinimumTaxReturnFormABN`: POST the return for the ABN. Documented responses: 201, 400, 401, 403, 404, 422, 500.
2. `requestGlobalDomesticGroupEntityTaxReturnForm`: POST each group-entity return under `{transactionID}` (spec: openapi/australian-taxation-office-global-domestic-minimum-group-entity-tax-return-openapi.yml). It returns 202.
3. These are lodgments with legal effect. An agent must act only for an authorised principal and must never resend a lodgment blindly after a timeout.
4. A 422 means a business-rule validation failure: correct the data before you resubmit.
