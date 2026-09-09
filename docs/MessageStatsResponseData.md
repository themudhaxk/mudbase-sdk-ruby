# Mudbase::MessageStatsResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_messages** | **Integer** |  | [optional] |
| **by_type** | [**MessageStatsResponseDataByType**](MessageStatsResponseDataByType.md) |  | [optional] |
| **by_status** | [**MessageStatsResponseDataByStatus**](MessageStatsResponseDataByStatus.md) |  | [optional] |
| **success_rate** | **Float** |  | [optional] |
| **period** | [**MessageStatsResponseDataPeriod**](MessageStatsResponseDataPeriod.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MessageStatsResponseData.new(
  total_messages: null,
  by_type: null,
  by_status: null,
  success_rate: null,
  period: null
)
```

