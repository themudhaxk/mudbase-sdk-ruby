# Mudbase::GetPermissionsMatrix200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **collections** | **Array&lt;Object&gt;** |  | [optional] |
| **roles** | **Array&lt;Object&gt;** |  | [optional] |
| **features** | **Array&lt;Object&gt;** | Per-role featurePermissions for app JWT gates | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPermissionsMatrix200ResponseData.new(
  collections: null,
  roles: null,
  features: null
)
```

