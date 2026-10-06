# Mudbase::ApproveRoleElevationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **approved** | **Boolean** |  |  |
| **reason** | **String** | Required if approved is false | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApproveRoleElevationRequest.new(
  approved: null,
  reason: null
)
```

