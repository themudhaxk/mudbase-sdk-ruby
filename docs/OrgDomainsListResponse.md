# Mudbase::OrgDomainsListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domains** | [**Array&lt;OrgDomainEntryOrgConsole&gt;**](OrgDomainEntryOrgConsole.md) |  | [optional] |
| **dns_verification_instructions** | **String** | Plain-language reminder to add the ownership TXT from each domain’s DNS checklist, then use Verify DNS in the organization’s domain settings. | [optional] |
| **primary_hostname** | **String** |  | [optional] |
| **api_base_url** | **String** |  | [optional] |
| **max_domains** | **Integer** |  | [optional] |
| **custom_domain_allowed** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgDomainsListResponse.new(
  domains: null,
  dns_verification_instructions: null,
  primary_hostname: null,
  api_base_url: null,
  max_domains: null,
  custom_domain_allowed: null
)
```

