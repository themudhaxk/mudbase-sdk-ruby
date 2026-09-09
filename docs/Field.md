# Mudbase::Field

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **type** | **String** |  |  |
| **required** | **Boolean** |  | [optional] |
| **unique** | **Boolean** |  | [optional] |
| **default** | [**FieldDefault**](FieldDefault.md) |  | [optional] |
| **validation** | **Object** |  | [optional] |
| **ui** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Field.new(
  name: null,
  type: null,
  required: null,
  unique: null,
  default: null,
  validation: null,
  ui: null
)
```

