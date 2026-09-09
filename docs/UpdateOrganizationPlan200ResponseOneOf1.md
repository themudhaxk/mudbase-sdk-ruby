# Mudbase::UpdateOrganizationPlan200ResponseOneOf1

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateOrganizationPlan200ResponseOneOf1.new(
  error: Plan upgrades must be done through the billing system,
  message: Please use /api/billing routes to upgrade your plan
)
```

