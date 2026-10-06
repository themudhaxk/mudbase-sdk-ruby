# Mudbase::MonitoringPerformanceResponseMetrics

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_requests** | **Integer** |  | [optional] |
| **avg_response_time** | **Float** |  | [optional] |
| **min_response_time** | **Float** |  | [optional] |
| **max_response_time** | **Float** |  | [optional] |
| **error_count** | **Integer** |  | [optional] |
| **success_count** | **Integer** |  | [optional] |
| **success_rate** | **Float** |  | [optional] |
| **error_rate** | **Float** |  | [optional] |
| **latency_source** | **String** | usage_stat when filled from UsageStat | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringPerformanceResponseMetrics.new(
  total_requests: null,
  avg_response_time: null,
  min_response_time: null,
  max_response_time: null,
  error_count: null,
  success_count: null,
  success_rate: null,
  error_rate: null,
  latency_source: null
)
```

