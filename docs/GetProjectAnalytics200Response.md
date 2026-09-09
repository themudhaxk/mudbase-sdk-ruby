# Mudbase::GetProjectAnalytics200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** |  | [optional] |
| **active_connections** | **Integer** |  | [optional] |
| **total_events** | **Integer** |  | [optional] |
| **last_activity** | **Time** |  | [optional] |
| **timestamp** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetProjectAnalytics200Response.new(
  project_id: null,
  active_connections: 42,
  total_events: 15234,
  last_activity: null,
  timestamp: null
)
```

