# Mudbase::CreateAnonymousSession200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **token** | **String** |  | [optional] |
| **refresh_token** | **String** | Refresh token for POST /api/auth/refresh | [optional] |
| **expires_in** | **Integer** |  | [optional] |
| **user** | [**CreateAnonymousSession200ResponseUser**](CreateAnonymousSession200ResponseUser.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateAnonymousSession200Response.new(
  message: Anonymous session created,
  token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...,
  refresh_token: null,
  expires_in: 86400,
  user: null
)
```

