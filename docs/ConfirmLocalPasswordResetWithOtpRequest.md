# Mudbase::ConfirmLocalPasswordResetWithOtpRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **project_id** | **String** |  |  |
| **otp** | **String** |  |  |
| **new_password** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfirmLocalPasswordResetWithOtpRequest.new(
  email: user@example.com,
  project_id: 65f1a2b3c4d5e6f7a8b9c0d1,
  otp: 123456,
  new_password: NewSecurePass123!
)
```

