# Mudbase::HealthResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **timestamp** | **Time** |  | [optional] |
| **services** | [**HealthResponseServices**](HealthResponseServices.md) |  | [optional] |
| **version** | **String** |  | [optional] |
| **uptime** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::HealthResponse.new(
  status: null,
  timestamp: null,
  services: null,
  version: null,
  uptime: null
)
```

