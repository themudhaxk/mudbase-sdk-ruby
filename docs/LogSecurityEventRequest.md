# Mudbase::LogSecurityEventRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **event_type** | **String** |  |  |
| **severity** | **String** |  |  |
| **details** | [**LogSecurityEventRequestDetails**](LogSecurityEventRequestDetails.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::LogSecurityEventRequest.new(
  event_type: unauthorized_access_attempt,
  severity: high,
  details: null
)
```

