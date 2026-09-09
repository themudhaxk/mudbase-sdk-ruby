# Mudbase::SendPushNotification429Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **success** | **Boolean** |  | [optional] |
| **error** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SendPushNotification429Response.new(
  success: null,
  error: messaging_rate_limited,
  message: null
)
```

