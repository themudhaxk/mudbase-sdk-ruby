# Mudbase::CreateApiKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **project_id** | **String** | MongoDB ObjectId of the project |  |
| **permissions** | [**Array&lt;ApiKeyPermission&gt;**](ApiKeyPermission.md) | Optional. Permission objects (resource + actions). Omit or pass [] for full access (all resources and actions). Include only the entries you want; remove resources or actions to restrict the key. | [optional] |
| **rate_limit** | [**RateLimit**](RateLimit.md) |  | [optional] |
| **expires_at** | **Time** | Optional. When provided, must be a valid ISO 8601 date-time in the future. Omit for no expiration. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateApiKeyRequest.new(
  name: null,
  project_id: null,
  permissions: null,
  rate_limit: null,
  expires_at: null
)
```

