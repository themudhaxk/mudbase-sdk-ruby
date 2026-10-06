# Mudbase::ApiGdprErasePostRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **confirm** | **String** | Must equal \&quot;DELETE\&quot; to proceed with erasure. |  |
| **current_password** | **String** | Required unless the account has no password set (OAuth-only) | [optional] |
| **totp_token** | **String** | Required only if the account has 2FA enabled | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiGdprErasePostRequest.new(
  confirm: null,
  current_password: CurrentPassword123!,
  totp_token: 123456
)
```

