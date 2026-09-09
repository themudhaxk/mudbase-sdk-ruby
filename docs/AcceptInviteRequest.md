# Mudbase::AcceptInviteRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **token** | **String** | Invitation token from the invite email link |  |
| **password** | **String** | Password for the new account |  |
| **first_name** | **String** |  |  |
| **last_name** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AcceptInviteRequest.new(
  token: null,
  password: null,
  first_name: null,
  last_name: null
)
```

