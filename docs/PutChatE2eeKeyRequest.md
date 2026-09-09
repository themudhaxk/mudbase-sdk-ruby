# Mudbase::PutChatE2eeKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **identity_public_key** | **String** | Base64-encoded public key (algorithm defined by client; opaque to server) |  |
| **key_version** | **Integer** | Optional; defaults to incrementing stored version | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::PutChatE2eeKeyRequest.new(
  identity_public_key: null,
  key_version: null
)
```

