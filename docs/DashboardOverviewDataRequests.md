# Mudbase::DashboardOverviewDataRequests

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **today** | **Integer** | Billing trackApiCall count (UTC day) | [optional] |
| **yesterday** | **Integer** |  | [optional] |
| **latency_tracked_today** | **Integer** | UsageStat latencyCount for this project (middleware-metered responses) | [optional] |
| **latency_tracked_yesterday** | **Integer** |  | [optional] |
| **metering_note** | **String** |  | [optional] |
| **change_pct** | **Float** |  | [optional] |
| **direction** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewDataRequests.new(
  today: null,
  yesterday: null,
  latency_tracked_today: null,
  latency_tracked_yesterday: null,
  metering_note: null,
  change_pct: null,
  direction: null
)
```

