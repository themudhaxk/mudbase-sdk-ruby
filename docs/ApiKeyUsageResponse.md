# Mudbase::ApiKeyUsageResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **usage** | [**ApiKeyUsage**](ApiKeyUsage.md) |  | [optional] |
| **rate_limit** | [**RateLimit**](RateLimit.md) |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiKeyUsageResponse.new(
  usage: null,
  rate_limit: null,
  is_active: null,
  expires_at: null
)
```

