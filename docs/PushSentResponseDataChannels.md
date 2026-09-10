# Mudbase::PushSentResponseDataChannels

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **fcm** | [**PushSentResponseDataChannelsFcm**](PushSentResponseDataChannelsFcm.md) |  | [optional] |
| **web_push** | [**PushSentResponseDataChannelsWebPush**](PushSentResponseDataChannelsWebPush.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PushSentResponseDataChannels.new(
  fcm: null,
  web_push: null
)
```

