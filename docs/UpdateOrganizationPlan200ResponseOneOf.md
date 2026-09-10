# Mudbase::UpdateOrganizationPlan200ResponseOneOf

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **org** | [**Organization**](Organization.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateOrganizationPlan200ResponseOneOf.new(
  message: Organization plan updated successfully,
  org: null
)
```

