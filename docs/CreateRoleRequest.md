# Mudbase::CreateRoleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **permissions** | [**Array&lt;CreateRoleRequestPermissionsInner&gt;**](CreateRoleRequestPermissionsInner.md) | Legacy resource-level permissions. For data CRUD, prefer &#x60;collectionPermissions&#x60; below. | [optional] |
| **hierarchy** | **Float** |  | [optional] |
| **collection_permissions** | [**Hash&lt;String, CreateRoleRequestCollectionPermissionsValue&gt;**](CreateRoleRequestCollectionPermissionsValue.md) | Per-collection CRUD map. Keys are collection slugs; value can be action array or object with actions + conditions. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateRoleRequest.new(
  name: Support Agent,
  description: Customer support team member,
  permissions: null,
  hierarchy: 40,
  collection_permissions: null
)
```

