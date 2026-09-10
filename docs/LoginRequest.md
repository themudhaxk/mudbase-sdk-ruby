# Mudbase::LoginRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::LoginRequest.new(
  email: john.doe@mudbase.dev,
  password: SecurePass123!
)
```

