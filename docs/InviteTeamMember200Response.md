# Mudbase::InviteTeamMember200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InviteTeamMember200Response.new(
  message: Invitation sent successfully,
  email: newuser@example.com,
  role: member
)
```

