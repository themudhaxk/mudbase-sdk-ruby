# Mudbase::DashboardOverviewDataLatencyInstanceRollup

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **scope** | **String** |  | [optional] |
| **p50_ms** | **Integer** |  | [optional] |
| **p95_ms** | **Integer** |  | [optional] |
| **p99_ms** | **Integer** |  | [optional] |
| **mean_ms** | **Integer** |  | [optional] |
| **samples_approx** | **Integer** |  | [optional] |
| **templates_tracked** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewDataLatencyInstanceRollup.new(
  scope: null,
  p50_ms: null,
  p95_ms: null,
  p99_ms: null,
  mean_ms: null,
  samples_approx: null,
  templates_tracked: null
)
```

