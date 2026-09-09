# Mudbase::ConvertAnonymousAccount200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **token** | **String** |  | [optional] |
| **refresh_token** | **String** |  | [optional] |
| **expires_in** | **Integer** |  | [optional] |
| **user** | [**User**](User.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConvertAnonymousAccount200Response.new(
  message: Account created successfully,
  token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...,
  refresh_token: null,
  expires_in: 1800,
  user: null
)
```

