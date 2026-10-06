# Mudbase::ProjectSmtpSettingsPublic

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **host** | **String** |  | [optional] |
| **port** | **Integer** |  | [optional] |
| **secure** | **Boolean** |  | [optional] |
| **auth_user** | **String** |  | [optional] |
| **has_password** | **Boolean** |  | [optional] |
| **from_name** | **String** |  | [optional] |
| **from_email** | **String** |  | [optional] |
| **domain_verified_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProjectSmtpSettingsPublic.new(
  enabled: null,
  host: null,
  port: null,
  secure: null,
  auth_user: null,
  has_password: null,
  from_name: null,
  from_email: null,
  domain_verified_at: null
)
```

