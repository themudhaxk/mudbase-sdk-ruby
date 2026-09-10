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
  project_id: 685ad30be129932fbb7a1047,
  otp: 123456,
  new_password: NewSecurePass123!
)
```

