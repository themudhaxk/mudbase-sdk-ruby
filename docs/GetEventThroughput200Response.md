# Mudbase::GetEventThroughput200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **window_ms** | **Integer** |  | [optional] |
| **total_events** | **Integer** |  | [optional] |
| **events_per_second** | **Float** |  | [optional] |
| **by_type** | **Hash&lt;String, Integer&gt;** |  | [optional] |
| **timestamp** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetEventThroughput200Response.new(
  window_ms: 60000,
  total_events: 523,
  events_per_second: 8.72,
  by_type: null,
  timestamp: null
)
```

