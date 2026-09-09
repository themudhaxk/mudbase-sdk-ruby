# Mudbase::Message

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |
| **title** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **recipients** | **Integer** |  | [optional] |
| **success_count** | **Integer** |  | [optional] |
| **failure_count** | **Integer** |  | [optional] |
| **status** | **String** |  | [optional] |
| **sent_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Message.new(
  _id: null,
  type: null,
  title: null,
  body: null,
  subject: null,
  recipients: null,
  success_count: null,
  failure_count: null,
  status: null,
  sent_at: null
)
```

