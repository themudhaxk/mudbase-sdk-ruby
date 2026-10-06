# Mudbase::GetBillingEstimate200ResponseSpendLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **soft_limit_cents** | **Float** |  | [optional] |
| **hard_limit_cents** | **Float** |  | [optional] |
| **spend_blocked** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetBillingEstimate200ResponseSpendLimits.new(
  soft_limit_cents: null,
  hard_limit_cents: null,
  spend_blocked: null
)
```

