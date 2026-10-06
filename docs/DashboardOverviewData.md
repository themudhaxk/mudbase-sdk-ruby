# Mudbase::DashboardOverviewData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project** | [**DashboardOverviewDataProject**](DashboardOverviewDataProject.md) |  | [optional] |
| **requests** | [**DashboardOverviewDataRequests**](DashboardOverviewDataRequests.md) |  | [optional] |
| **active_users** | [**DashboardOverviewDataActiveUsers**](DashboardOverviewDataActiveUsers.md) |  | [optional] |
| **latency** | [**DashboardOverviewDataLatency**](DashboardOverviewDataLatency.md) |  | [optional] |
| **uptime** | [**DashboardOverviewDataUptime**](DashboardOverviewDataUptime.md) |  | [optional] |
| **request_volume14d** | [**Array&lt;DashboardOverviewDataRequestVolume14dInner&gt;**](DashboardOverviewDataRequestVolume14dInner.md) |  | [optional] |
| **recent_activity** | [**Array&lt;DashboardActivityItem&gt;**](DashboardActivityItem.md) |  | [optional] |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::DashboardOverviewData.new(
  project: null,
  requests: null,
  active_users: null,
  latency: null,
  uptime: null,
  request_volume14d: null,
  recent_activity: null,
  generated_at: null
)
```

