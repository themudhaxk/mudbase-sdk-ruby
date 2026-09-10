# Mudbase::RegisterLocalUser201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **require_verification** | **Boolean** | true when email verification is required; no token in response | [optional] |
| **token** | **String** | Present only when requireEmailVerification is false | [optional] |
| **refresh_token** | **String** | Present only when requireEmailVerification is false | [optional] |
| **expires_in** | **Integer** | Present only when token is returned | [optional] |
| **user** | [**RegisterLocalUser201ResponseUser**](RegisterLocalUser201ResponseUser.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RegisterLocalUser201Response.new(
  message: null,
  require_verification: null,
  token: null,
  refresh_token: null,
  expires_in: null,
  user: null
)
```

