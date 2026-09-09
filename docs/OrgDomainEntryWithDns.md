# Mudbase::OrgDomainEntryWithDns

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** | Subdocument id when present (MongoDB) | [optional] |
| **hostname** | **String** |  | [optional] |
| **hostname_normalized** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **is_primary** | **Boolean** |  | [optional] |
| **source** | **String** |  | [optional] |
| **verification_token** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **verified_at** | **Time** |  | [optional] |
| **last_verified_at** | **Time** |  | [optional] |
| **dns_txt_host** | **String** | FQDN for the TXT record (e.g. _mudbase-verify.example.com) | [optional] |
| **dns_txt_value** | **String** | Exact TXT string value (mudbase-domain-verification&#x3D;&lt;token&gt;) | [optional] |
| **edge** | [**OrgEdgeHints**](OrgEdgeHints.md) |  | [optional] |
| **platform_activation_pending** | **Boolean** | True while Mudbase TXT passed but custom host not yet active (includes CNAME and platform DNS pipeline). | [optional] |
| **custom_domain_live_for_api_traffic** | **Boolean** |  | [optional] |
| **custom_domain_verification_step** | **Integer** | Console wizard step 1–3; null when active/verified. | [optional] |
| **routing_cname_target** | **String** | Routing CNAME target: the managed certificate&#39;s provisioned CNAME target when requirements have been stored; otherwise the platform default target. | [optional] |
| **dns_records** | [**Array&lt;OrgDnsRecord&gt;**](OrgDnsRecord.md) | Unified checklist: Mudbase ownership TXT, routing CNAME (purpose &#x60;routing&#x60;) when provisioned else the platform default, and the managed certificate-provisioning rows once the managed certificate has been provisioned after the Mudbase TXT. Empty or absent when the certificate is not yet provisioned. Prefer this over &#x60;platformDnsVerification&#x60; alone for org-facing DNS UI. | [optional] |
| **fly_certificate_status** | **String** | Managed certificate &#x60;status&#x60; during provisioning (e.g. &#x60;pending_validation&#x60;, &#x60;active&#x60;). Null when managed certificate provisioning is not in use for this deployment. | [optional] |
| **platform_dns_verification** | [**OrgPlatformDnsVerificationCustomer**](OrgPlatformDnsVerificationCustomer.md) |  | [optional] |
| **cname_submitted_at** | **Time** |  | [optional] |
| **cname_approved_at** | **Time** |  | [optional] |
| **platform_dns_verification_submitted_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgDomainEntryWithDns.new(
  _id: null,
  hostname: null,
  hostname_normalized: null,
  status: null,
  is_primary: null,
  source: null,
  verification_token: null,
  created_at: null,
  verified_at: null,
  last_verified_at: null,
  dns_txt_host: null,
  dns_txt_value: null,
  edge: null,
  platform_activation_pending: null,
  custom_domain_live_for_api_traffic: null,
  custom_domain_verification_step: null,
  routing_cname_target: null,
  dns_records: null,
  fly_certificate_status: null,
  platform_dns_verification: null,
  cname_submitted_at: null,
  cname_approved_at: null,
  platform_dns_verification_submitted_at: null
)
```

