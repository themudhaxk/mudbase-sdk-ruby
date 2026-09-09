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
  project_id: 685ad30be129932fbb7a1047,
  device_id: device-uuid-123
)
```

