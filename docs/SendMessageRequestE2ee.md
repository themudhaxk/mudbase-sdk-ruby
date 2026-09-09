# Mudbase::SendMessageRequestE2ee

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **version** | **Integer** |  | [optional][default to 1] |
| **scheme** | **String** |  | [optional] |
| **ciphertext** | **String** | Base64-encoded ciphertext | [optional] |
| **nonce** | **String** |  | [optional] |
| **ephemeral_public_key** | **String** |  | [optional] |
| **sender_key_id** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SendMessageRequestE2ee.new(
  version: null,
  scheme: mudbase-e2ee-v1,
  ciphertext: null,
  nonce: null,
  ephemeral_public_key: null,
  sender_key_id: null
)
```

