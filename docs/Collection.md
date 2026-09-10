# Mudbase::Collection

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **project** | **String** |  | [optional] |
| **fields** | [**Array&lt;Field&gt;**](Field.md) |  | [optional] |
| **permissions** | [**Array&lt;Permission&gt;**](Permission.md) |  | [optional] |
| **settings** | **Object** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Collection.new(
  _id: null,
  name: null,
  slug: null,
  project: null,
  fields: null,
  permissions: null,
  settings: null,
  created_at: null,
  updated_at: null
)
```

