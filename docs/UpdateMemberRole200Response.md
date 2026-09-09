# Mudbase::UpdateMemberRole200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **user** | [**User**](User.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateMemberRole200Response.new(
  message: Role updated successfully,
  user: null
)
```

