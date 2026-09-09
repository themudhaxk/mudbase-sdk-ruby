# Mudbase::AcceptInvite201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **token** | **String** | JWT for the new user session | [optional] |
| **user** | [**AcceptInvite201ResponseUser**](AcceptInvite201ResponseUser.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AcceptInvite201Response.new(
  message: null,
  token: null,
  user: null
)
```

