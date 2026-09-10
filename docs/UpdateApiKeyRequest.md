# Mudbase::UpdateApiKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **permissions** | [**Array&lt;ApiKeyPermission&gt;**](ApiKeyPermission.md) |  | [optional] |
| **rate_limit** | [**RateLimit**](RateLimit.md) |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateApiKeyRequest.new(
  name: null,
  permissions: null,
  rate_limit: null,
  is_active: null
)
```

