# Mudbase::Disable2FARequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **password** | **String** |  |  |
| **token** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Disable2FARequest.new(
  password: SecurePass123!,
  token: 123456
)
```

