# Mudbase::MonitoringLogsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **logs** | [**Array&lt;MonitoringLogsResponseLogsInner&gt;**](MonitoringLogsResponseLogsInner.md) |  | [optional] |
| **count** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **total_pages** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringLogsResponse.new(
  logs: null,
  count: null,
  page: null,
  limit: null,
  total: null,
  total_pages: null
)
```

