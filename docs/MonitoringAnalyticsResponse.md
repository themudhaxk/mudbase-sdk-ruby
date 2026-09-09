# Mudbase::MonitoringAnalyticsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **period** | **String** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **days** | **Integer** | Present when rolling window used | [optional] |
| **stats** | [**Array&lt;MonitoringAnalyticsResponseStatsInner&gt;**](MonitoringAnalyticsResponseStatsInner.md) |  | [optional] |
| **totals** | [**MonitoringAnalyticsResponseTotals**](MonitoringAnalyticsResponseTotals.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringAnalyticsResponse.new(
  period: null,
  granularity: null,
  days: null,
  stats: null,
  totals: null
)
```

