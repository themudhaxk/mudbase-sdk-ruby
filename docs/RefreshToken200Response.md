# Mudbase::RefreshToken200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **token** | **String** | New JWT access token | [optional] |
| **refresh_token** | **String** | New refresh token (store and use for next refresh) | [optional] |
| **expires_in** | **Integer** | Access token TTL in seconds | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RefreshToken200Response.new(
  message: Token refreshed successfully,
  token: null,
  refresh_token: null,
  expires_in: 1800
)
```

