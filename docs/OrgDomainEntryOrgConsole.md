# Mudbase::OrgDomainEntryOrgConsole

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **hostname** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **is_primary** | **Boolean** |  | [optional] |
| **source** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **verified_at** | **Time** |  | [optional] |
| **last_verified_at** | **Time** |  | [optional] |
| **cname_submitted_at** | **Time** |  | [optional] |
| **cname_approved_at** | **Time** |  | [optional] |
| **custom_domain_verification_step** | **Integer** |  | [optional] |
| **routing_cname_target** | **String** |  | [optional] |
| **dns_records** | [**Array&lt;OrgDnsRecord&gt;**](OrgDnsRecord.md) |  | [optional] |
| **platform_activation_pending** | **Boolean** |  | [optional] |
| **custom_domain_live_for_api_traffic** | **Boolean** |  | [optional] |
| **edge** | [**OrgEdgeHints**](OrgEdgeHints.md) |  | [optional] |
| **fly_certificate_status** | **String** |  | [optional] |
| **platform_dns_verification** | [**OrgPlatformDnsVerificationCustomer**](OrgPlatformDnsVerificationCustomer.md) |  | [optional] |
| **platform_dns_verification_submitted_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgDomainEntryOrgConsole.new(
  _id: null,
  hostname: null,
  status: null,
  is_primary: null,
  source: null,
  created_at: null,
  verified_at: null,
  last_verified_at: null,
  cname_submitted_at: null,
  cname_approved_at: null,
  custom_domain_verification_step: null,
  routing_cname_target: null,
  dns_records: null,
  platform_activation_pending: null,
  custom_domain_live_for_api_traffic: null,
  edge: null,
  fly_certificate_status: null,
  platform_dns_verification: null,
  platform_dns_verification_submitted_at: null
)
```

