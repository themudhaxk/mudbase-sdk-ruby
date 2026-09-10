# Mudbase::WebhookStatsResponseEventStatsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** | Event name | [optional] |
| **count** | **Integer** |  | [optional] |
| **success_rate** | **Float** | Fraction of logs with status success (0–1) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookStatsResponseEventStatsInner.new(
  _id: null,
  count: null,
  success_rate: null
)
```

