# Mudbase::ProjectSmtpTestRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | **String** | Recipient for verification and test message |  |
| **use_saved** | **Boolean** | When true, use saved SMTP config; otherwise supply host/auth fields below | [optional][default to true] |
| **host** | **String** |  | [optional] |
| **port** | **Integer** |  | [optional] |
| **secure** | **Boolean** |  | [optional] |
| **auth_user** | **String** |  | [optional] |
| **auth_pass** | **String** |  | [optional] |
| **from_email** | **String** |  | [optional] |
| **from_name** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ProjectSmtpTestRequest.new(
  to: null,
  use_saved: null,
  host: null,
  port: null,
  secure: null,
  auth_user: null,
  auth_pass: null,
  from_email: null,
  from_name: null
)
```

