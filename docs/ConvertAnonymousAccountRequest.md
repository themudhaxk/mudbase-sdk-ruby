# Mudbase::ConvertAnonymousAccountRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **password** | **String** |  |  |
| **first_name** | **String** |  | [optional] |
| **last_name** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConvertAnonymousAccountRequest.new(
  email: user@example.com,
  password: SecurePassword123!,
  first_name: John,
  last_name: Doe
)
```

