# Mudbase::RegisterWithRole201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **require_verification** | **Boolean** | True when the project requires email verification before a session is issued - no token is returned in that case. | [optional] |
| **token** | **String** | JWT access token. Absent when requireVerification is true. | [optional] |
| **refresh_token** | **String** | JWT refresh token. Absent when requireVerification is true. | [optional] |
| **expires_in** | **Integer** | Access token TTL in seconds. Absent when requireVerification is true. | [optional] |
| **user** | [**RegisterWithRole201ResponseUser**](RegisterWithRole201ResponseUser.md) |  | [optional] |
| **role** | [**RegisterWithRole201ResponseRole**](RegisterWithRole201ResponseRole.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RegisterWithRole201Response.new(
  message: null,
  require_verification: null,
  token: null,
  refresh_token: null,
  expires_in: null,
  user: null,
  role: null
)
```

