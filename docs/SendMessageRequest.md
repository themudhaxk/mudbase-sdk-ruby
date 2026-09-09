# Mudbase::SendMessageRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  |  |
| **content** | **String** | Plaintext body; omit when sending e2ee (use e2ee.ciphertext for E2EE text) | [optional] |
| **e2ee** | [**SendMessageRequestE2ee**](SendMessageRequestE2ee.md) |  | [optional] |
| **reply_to** | **String** |  | [optional] |
| **mentions** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SendMessageRequest.new(
  type: null,
  content: null,
  e2ee: null,
  reply_to: null,
  mentions: null
)
```

