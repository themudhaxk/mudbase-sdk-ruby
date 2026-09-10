# Mudbase::MonitoringPerformanceResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **period** | **String** |  | [optional] |
| **metrics** | [**MonitoringPerformanceResponseMetrics**](MonitoringPerformanceResponseMetrics.md) |  | [optional] |
| **top_endpoints** | **Array&lt;Object&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringPerformanceResponse.new(
  period: null,
  metrics: null,
  top_endpoints: null
)
```

