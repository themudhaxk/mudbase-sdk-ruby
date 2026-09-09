# Mudbase::LogSecurityEventRequestDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **String** |  | [optional] |
| **resource** | **String** |  | [optional] |
| **ip_address** | **String** |  | [optional] |
| **user_agent** | **String** |  | [optional] |
| **action** | **String** |  | [optional] |
| **reason** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::LogSecurityEventRequestDetails.new(
  user_id: null,
  resource: null,
  ip_address: null,
  user_agent: null,
  action: null,
  reason: null
)
```

