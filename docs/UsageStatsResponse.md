# Mudbase::UsageStatsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **usage** | [**Usage**](Usage.md) |  | [optional] |
| **limits** | [**Limits**](Limits.md) |  | [optional] |
| **plan** | [**Plan**](Plan.md) |  | [optional] |
| **period** | **String** |  | [optional] |
| **percentages** | [**UsageStatsResponsePercentages**](UsageStatsResponsePercentages.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UsageStatsResponse.new(
  usage: null,
  limits: null,
  plan: null,
  period: null,
  percentages: null
)
```

