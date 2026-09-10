# Mudbase::OrgVerifyCustomDomainDnsFailureResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  |  |
| **code** | **String** |  |  |
| **error** | **String** |  |  |
| **challenge_host** | **String** |  |  |
| **expected_txt** | **String** |  |  |
| **dns_txt_host** | **String** |  |  |
| **dns_txt_value** | **String** |  |  |
| **status** | **String** |  |  |
| **verification_token** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::OrgVerifyCustomDomainDnsFailureResponse.new(
  success: null,
  code: dns_verification_failed,
  error: null,
  challenge_host: null,
  expected_txt: null,
  dns_txt_host: null,
  dns_txt_value: null,
  status: null,
  verification_token: null
)
```

