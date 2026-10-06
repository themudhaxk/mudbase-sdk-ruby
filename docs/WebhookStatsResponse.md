# Mudbase::WebhookStatsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status_stats** | [**Array&lt;WebhookStatsResponseStatusStatsInner&gt;**](WebhookStatsResponseStatusStatsInner.md) | Grouped by delivery status |  |
| **event_stats** | [**Array&lt;WebhookStatsResponseEventStatsInner&gt;**](WebhookStatsResponseEventStatsInner.md) | Grouped by event name |  |
| **period** | **String** |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookStatsResponse.new(
  status_stats: null,
  event_stats: null,
  period: 7 days
)
```

