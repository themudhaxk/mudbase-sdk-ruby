# Mudbase::ApiKeyWithSecret

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **project** | [**ProjectSummary**](ProjectSummary.md) |  | [optional] |
| **permissions** | [**Array&lt;ApiKeyPermission&gt;**](ApiKeyPermission.md) |  | [optional] |
| **rate_limit** | [**RateLimit**](RateLimit.md) |  | [optional] |
| **usage** | [**ApiKeyUsage**](ApiKeyUsage.md) |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **expires_at** | **Time** |  | [optional] |
| **created_by** | [**UserSummary**](UserSummary.md) |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **secret** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiKeyWithSecret.new(
  _id: null,
  name: null,
  project: null,
  permissions: null,
  rate_limit: null,
  usage: null,
  is_active: null,
  expires_at: null,
  created_by: null,
  created_at: null,
  secret: null
)
```

