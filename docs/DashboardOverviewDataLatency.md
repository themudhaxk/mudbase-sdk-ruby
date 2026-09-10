# Mudbase::DashboardOverviewDataLatency

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **scope** | **String** |  | [optional] |
| **avg_ms_today** | **Integer** |  | [optional] |
| **avg_ms7d** | **Integer** |  | [optional] |
| **latency_samples_today** | **Integer** | Count of openapi-docs–scoped latency samples for this project (UTC today) | [optional] |
| **latency_needs_traffic** | **Boolean** |  | [optional] |
| **interpretation** | **String** | Why mean can differ from typical latency; points to latency-insights | [optional] |
| **instance_rollup** | [**DashboardOverviewDataLatencyInstanceRollup**](DashboardOverviewDataLatencyInstanceRollup.md) |  | [optional] |
| **top_routes_by_impact_hint** | [**Array&lt;DashboardOverviewDataLatencyTopRoutesByImpactHintInner&gt;**](DashboardOverviewDataLatencyTopRoutesByImpactHintInner.md) | Top route templates by impact score on this instance (debugging hint) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewDataLatency.new(
  scope: null,
  avg_ms_today: null,
  avg_ms7d: null,
  latency_samples_today: null,
  latency_needs_traffic: null,
  interpretation: null,
  instance_rollup: null,
  top_routes_by_impact_hint: null
)
```

