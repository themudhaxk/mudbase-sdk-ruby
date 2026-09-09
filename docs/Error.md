# Mudbase::Error

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error** | **String** |  | [optional] |
| **code** | **String** |  | [optional] |
| **details** | [**ErrorDetails**](ErrorDetails.md) |  | [optional] |
| **timestamp** | **Time** |  | [optional] |
| **path** | **String** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Error.new(
  error: null,
  code: null,
  details: null,
  timestamp: null,
  path: null,
  request_id: null
)
```

