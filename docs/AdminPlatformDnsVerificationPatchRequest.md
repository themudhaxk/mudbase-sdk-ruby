# Mudbase::AdminPlatformDnsVerificationPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **record_type** | **String** |  | [optional] |
| **record_name** | **String** |  |  |
| **record_value** | **String** |  |  |
| **ttl_seconds** | **Integer** |  | [optional] |
| **staff_note** | **String** |  | [optional] |
| **reset_customer_platform_dns_submission** | **Boolean** |  | [optional] |
| **notify_org** | **Boolean** | When not false (default), email org billing contact with step-3 DNS instructions after save. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AdminPlatformDnsVerificationPatchRequest.new(
  record_type: null,
  record_name: null,
  record_value: null,
  ttl_seconds: null,
  staff_note: null,
  reset_customer_platform_dns_submission: null,
  notify_org: null
)
```

