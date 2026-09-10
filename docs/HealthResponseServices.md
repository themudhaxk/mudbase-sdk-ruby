# Mudbase::HealthResponseServices

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **database** | **String** |  | [optional] |
| **redis** | **String** |  | [optional] |
| **storage** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **sms** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::HealthResponseServices.new(
  database: null,
  redis: null,
  storage: null,
  email: null,
  sms: null
)
```

