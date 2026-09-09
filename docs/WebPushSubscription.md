# Mudbase::WebPushSubscription

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **endpoint** | **String** | The push-service endpoint URL returned by &#x60;pushManager.subscribe()&#x60;. |  |
| **keys** | [**WebPushSubscriptionKeys**](WebPushSubscriptionKeys.md) |  |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushSubscription.new(
  endpoint: null,
  keys: null
)
```

