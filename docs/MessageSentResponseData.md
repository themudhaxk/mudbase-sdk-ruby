# Mudbase::MessageSentResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **recipients** | **Integer** |  | [optional] |
| **success_count** | **Integer** |  | [optional] |
| **failure_count** | **Integer** |  | [optional] |
| **message_id** | **String** |  | [optional] |
| **sent_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MessageSentResponseData.new(
  _id: null,
  type: null,
  status: null,
  recipients: null,
  success_count: null,
  failure_count: null,
  message_id: null,
  sent_at: null
)
```

