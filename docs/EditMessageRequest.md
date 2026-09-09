# Mudbase::EditMessageRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content** | **String** | New plaintext (non-E2EE messages only) | [optional] |
| **e2ee** | [**EditMessageRequestE2ee**](EditMessageRequestE2ee.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EditMessageRequest.new(
  content: null,
  e2ee: null
)
```

