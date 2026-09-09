# Mudbase::PushSentResponseDataChannelsWebPush

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success_count** | **Integer** |  | [optional] |
| **failure_count** | **Integer** |  | [optional] |
| **pruned** | **Integer** | Subscriptions the push service reported as gone (404/410) and that were pruned during this send.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PushSentResponseDataChannelsWebPush.new(
  success_count: null,
  failure_count: null,
  pruned: null
)
```

