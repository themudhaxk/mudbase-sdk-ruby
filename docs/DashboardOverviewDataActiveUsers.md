# Mudbase::DashboardOverviewDataActiveUsers

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **last24h** | **Integer** |  | [optional] |
| **last7d** | **Integer** |  | [optional] |
| **last30d** | **Integer** |  | [optional] |
| **change_pct7d** | **Float** |  | [optional] |
| **direction7d** | **String** |  | [optional] |
| **realtime_connected** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewDataActiveUsers.new(
  last24h: null,
  last7d: null,
  last30d: null,
  change_pct7d: null,
  direction7d: null,
  realtime_connected: null
)
```

