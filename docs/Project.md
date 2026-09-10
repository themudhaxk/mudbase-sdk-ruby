# Mudbase::Project

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **org** | **String** |  | [optional] |
| **auth** | [**AuthConfig**](AuthConfig.md) |  | [optional] |
| **database** | [**DatabaseConfig**](DatabaseConfig.md) |  | [optional] |
| **storage** | [**StorageConfig**](StorageConfig.md) |  | [optional] |
| **settings** | [**ProjectSettings**](ProjectSettings.md) |  | [optional] |
| **usage** | [**ProjectUsage**](ProjectUsage.md) |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Project.new(
  _id: null,
  name: null,
  description: null,
  slug: null,
  org: null,
  auth: null,
  database: null,
  storage: null,
  settings: null,
  usage: null,
  created_at: null,
  updated_at: null
)
```

