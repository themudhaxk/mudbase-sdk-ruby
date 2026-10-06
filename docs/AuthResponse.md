# Mudbase::AuthResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **token** | **String** | JWT access token (use in Authorization Bearer header) | [optional] |
| **refresh_token** | **String** | JWT refresh token (use with POST /api/auth/refresh to get new token pair) | [optional] |
| **expires_in** | **Integer** | Access token TTL in seconds (e.g. 1800 for 30 minutes) | [optional] |
| **user** | [**User**](User.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AuthResponse.new(
  message: null,
  token: null,
  refresh_token: null,
  expires_in: null,
  user: null
)
```

