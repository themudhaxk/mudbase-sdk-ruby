# Mudbase::UpdateRoleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **permissions** | **Array&lt;Object&gt;** |  | [optional] |
| **hierarchy** | **Float** |  | [optional] |
| **is_active** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateRoleRequest.new(
  name: Support Agent,
  description: Customer support team member with enhanced permissions,
  permissions: null,
  hierarchy: 45,
  is_active: true
)
```

