# Mudbase::UpdateCollectionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **fields** | [**Array&lt;Field&gt;**](Field.md) |  | [optional] |
| **permissions** | [**Array&lt;Permission&gt;**](Permission.md) |  | [optional] |
| **settings** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateCollectionRequest.new(
  name: null,
  fields: null,
  permissions: null,
  settings: null
)
```

