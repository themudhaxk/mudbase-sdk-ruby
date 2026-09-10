# Mudbase::MonitoringLogsResponseLogsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  | [optional] |
| **timestamp** | **Time** |  | [optional] |
| **level** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |
| **action** | **String** |  | [optional] |
| **activity_title** | **String** |  | [optional] |
| **activity_detail** | **String** |  | [optional] |
| **user** | [**MonitoringLogsResponseLogsInnerUser**](MonitoringLogsResponseLogsInnerUser.md) |  | [optional] |
| **project** | **Object** |  | [optional] |
| **metadata** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringLogsResponseLogsInner.new(
  id: null,
  timestamp: null,
  level: null,
  message: null,
  action: null,
  activity_title: null,
  activity_detail: null,
  user: null,
  project: null,
  metadata: null
)
```

