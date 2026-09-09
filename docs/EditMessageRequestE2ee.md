# Mudbase::EditMessageRequestE2ee

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **version** | **Integer** |  | [optional] |
| **scheme** | **String** |  | [optional] |
| **ciphertext** | **String** |  | [optional] |
| **nonce** | **String** |  | [optional] |
| **ephemeral_public_key** | **String** |  | [optional] |
| **sender_key_id** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EditMessageRequestE2ee.new(
  version: null,
  scheme: null,
  ciphertext: null,
  nonce: null,
  ephemeral_public_key: null,
  sender_key_id: null
)
```

