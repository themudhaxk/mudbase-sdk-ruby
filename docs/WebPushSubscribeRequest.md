# Mudbase::WebPushSubscribeRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subscription** | [**WebPushSubscription**](WebPushSubscription.md) |  |  |
| **user_id** | **String** | Optional end-user id to associate with this subscription, for targeted sends. | [optional] |
| **device_id** | **String** | Optional client-supplied device identifier. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushSubscribeRequest.new(
  subscription: null,
  user_id: null,
  device_id: null
)
```

