# Mudbase::InviteSubOrganizationMember200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **role** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InviteSubOrganizationMember200Response.new(
  message: Invitation sent successfully,
  email: user@suborg.example.com,
  role: viewer
)
```

