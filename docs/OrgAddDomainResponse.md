# Mudbase::OrgAddDomainResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **domain** | [**OrgDomainEntryOrgConsole**](OrgDomainEntryOrgConsole.md) |  |  |
| **dns_verification_instructions** | **String** | Plain-language reminder to add the ownership TXT from the domain’s DNS checklist, then use Verify DNS in the organization’s domain settings. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgAddDomainResponse.new(
  success: null,
  domain: null,
  dns_verification_instructions: null
)
```

