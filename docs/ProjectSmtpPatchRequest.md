# Mudbase::ProjectSmtpPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **host** | **String** |  | [optional] |
| **port** | **Integer** |  | [optional] |
| **secure** | **Boolean** |  | [optional] |
| **auth_user** | **String** |  | [optional] |
| **auth_pass** | **String** | SMTP password; stored encrypted, never returned on GET | [optional] |
| **from_name** | **String** |  | [optional] |
| **from_email** | **String** |  | [optional] |
| **domain_verified_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProjectSmtpPatchRequest.new(
  enabled: null,
  host: null,
  port: null,
  secure: null,
  auth_user: null,
  auth_pass: null,
  from_name: null,
  from_email: null,
  domain_verified_at: null
)
```

