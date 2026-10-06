# Mudbase::CreateRole201ResponseRole

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **permissions** | [**Array&lt;CreateRole201ResponseRolePermissionsInner&gt;**](CreateRole201ResponseRolePermissionsInner.md) |  | [optional] |
| **hierarchy** | **Float** |  | [optional] |
| **is_system** | **Boolean** |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateRole201ResponseRole.new(
  _id: null,
  name: null,
  slug: null,
  description: null,
  permissions: null,
  hierarchy: null,
  is_system: null,
  is_active: null
)
```

