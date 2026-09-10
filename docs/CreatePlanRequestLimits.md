# Mudbase::CreatePlanRequestLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_calls** | **Float** |  | [optional] |
| **storage** | **Float** |  | [optional] |
| **bandwidth** | **Float** |  | [optional] |
| **users** | **Float** |  | [optional] |
| **custom_limits** | [**Array&lt;CreatePlanRequestLimitsCustomLimitsInner&gt;**](CreatePlanRequestLimitsCustomLimitsInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreatePlanRequestLimits.new(
  api_calls: null,
  storage: null,
  bandwidth: null,
  users: null,
  custom_limits: null
)
```

