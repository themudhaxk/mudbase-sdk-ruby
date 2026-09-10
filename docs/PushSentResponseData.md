# Mudbase::PushSentResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** | True when at least one recipient across any channel was delivered to. | [optional] |
| **message_id** | **String** |  | [optional] |
| **success_count** | **Integer** |  | [optional] |
| **failure_count** | **Integer** |  | [optional] |
| **channels** | [**PushSentResponseDataChannels**](PushSentResponseDataChannels.md) |  | [optional] |
| **rejected_tokens** | **Array&lt;String&gt;** | Device tokens that were passed but are not registered to the project, and so were dropped. Omitted when empty.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PushSentResponseData.new(
  success: null,
  message_id: null,
  success_count: null,
  failure_count: null,
  channels: null,
  rejected_tokens: null
)
```

