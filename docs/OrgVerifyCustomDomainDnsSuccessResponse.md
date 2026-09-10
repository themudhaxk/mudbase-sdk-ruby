# Mudbase::OrgVerifyCustomDomainDnsSuccessResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **hostname** | **String** |  |  |
| **status** | **String** | Domain row status after check (typically cname_pending_staff after first TXT success from pending/failed; legacy dns_verified possible) |  |
| **verification_token** | **String** |  |  |
| **challenge_host** | **String** | Same as dnsTxtHost (_mudbase-verify.&lt;hostname&gt;) |  |
| **expected_txt** | **String** | Same as dnsTxtValue |  |
| **dns_txt_host** | **String** |  |  |
| **dns_txt_value** | **String** |  |  |
| **edge** | [**OrgEdgeHints**](OrgEdgeHints.md) |  | [optional] |
| **dns_records** | [**Array&lt;OrgDnsRecord&gt;**](OrgDnsRecord.md) | Same shape as &#x60;OrgDomainEntryWithDns.dnsRecords&#x60; when certificate provisioning ran after this successful verify; omit or empty when provisioning is disabled or not yet run. | [optional] |
| **fly_certificate_status** | **String** | Managed certificate status after verify when provisioning is active; null otherwise | [optional] |
| **fly_acme_enabled** | **Boolean** | True when automated managed-certificate provisioning is configured for this deployment. | [optional] |
| **fly_acme_disabled_reason** | **String** | When &#x60;flyAcmeEnabled&#x60; is false, why automated provisioning did not run (ops misconfiguration hint). | [optional] |
| **fly_provision_error** | **String** | When provisioning is enabled but certificate issuance failed, the provider error message for support; null on success. | [optional] |
| **fly_legacy_staff_pipeline** | **Boolean** | When true, the legacy staff pipeline is on: status may stay &#x60;cname_pending_staff&#x60; and staff approve-cname is required even if certificate provisioning succeeds. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgVerifyCustomDomainDnsSuccessResponse.new(
  success: null,
  hostname: null,
  status: null,
  verification_token: null,
  challenge_host: null,
  expected_txt: null,
  dns_txt_host: null,
  dns_txt_value: null,
  edge: null,
  dns_records: null,
  fly_certificate_status: null,
  fly_acme_enabled: null,
  fly_acme_disabled_reason: null,
  fly_provision_error: null,
  fly_legacy_staff_pipeline: null
)
```

