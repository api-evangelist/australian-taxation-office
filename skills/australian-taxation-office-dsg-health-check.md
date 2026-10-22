---
name: dsg-health-check
description: Check that the ATO Digital Service Gateway is up and that the caller is authorised for a given ABN/WPN and TFN.
api: openapi/australian-taxation-office-health-check-openapi.yml
operations:
- GetStatus
- GetHeartbeat
- GetHeartbeatABN
- GetHeartbeatWPN
generated: '2026-10-22'
method: generated
---

# Check that the ATO Digital Service Gateway is up and that the caller is authorised for a given ABN/WPN and TFN.

Skill generated from the published ATO API Portal spec. No provider-published skills or AGENTS.md were found (https://apiportal.ato.gov.au/AGENTS.md returned 404).

1. `GetStatus` / `GetHeartbeat`: confirm that the DSG and the API are running.
2. Using an OAuth2 client-credentials token (scope `ato.healthcheck.*.*`), call `GetHeartbeatABN` or `GetHeartbeatWPN` to confirm authorisation for the business and individual.
3. Documented responses: 200 and 400. All of these calls are read-only and safe to retry.
