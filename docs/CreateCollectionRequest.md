# Mudbase::CreateCollectionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **slug** | **String** |  | [optional] |
| **fields** | [**Array&lt;Field&gt;**](Field.md) |  |  |
| **permissions** | [**Array&lt;Permission&gt;**](Permission.md) |  | [optional] |
| **settings** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateCollectionRequest.new(
  name: null,
  slug: null,
  fields: null,
  permissions: null,
  settings: null
)
```

