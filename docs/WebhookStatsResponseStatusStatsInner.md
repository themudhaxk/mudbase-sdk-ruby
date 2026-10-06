# Mudbase::WebhookStatsResponseStatusStatsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** | Status key (pending, success, failed, retrying) | [optional] |
| **count** | **Integer** |  | [optional] |
| **avg_duration** | **Float** | Average duration in ms for that status bucket | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookStatsResponseStatusStatsInner.new(
  _id: null,
  count: null,
  avg_duration: null
)
```

