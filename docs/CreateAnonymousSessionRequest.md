# Mudbase::CreateAnonymousSessionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** | Project ID for the anonymous session | [optional] |
| **device_id** | **String** | Optional device identifier | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateAnonymousSessionRequest.new(
  project_id: 65f1a2b3c4d5e6f7a8b9c0d1,
  device_id: device-uuid-123
)
```

