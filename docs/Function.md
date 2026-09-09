# Mudbase::Function

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **project_id** | **String** |  | [optional] |
| **trigger** | [**FunctionTrigger**](FunctionTrigger.md) |  | [optional] |
| **stats** | [**FunctionStats**](FunctionStats.md) |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |
| **created_by** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Function.new(
  _id: null,
  name: null,
  description: null,
  project_id: null,
  trigger: null,
  stats: null,
  is_active: null,
  created_by: null,
  created_at: null,
  updated_at: null
)
```

