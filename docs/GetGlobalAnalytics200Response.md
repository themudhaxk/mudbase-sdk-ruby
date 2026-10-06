# Mudbase::GetGlobalAnalytics200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **active_connections** | **Integer** |  | [optional] |
| **peak_connections** | **Integer** |  | [optional] |
| **total_events** | **Integer** |  | [optional] |
| **events_per_minute** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetGlobalAnalytics200Response.new(
  active_connections: null,
  peak_connections: null,
  total_events: null,
  events_per_minute: null
)
```

