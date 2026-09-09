# Mudbase::GetProjectUsers200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **users** | [**Array&lt;GetOrganizationUsers200ResponseUsersInner&gt;**](GetOrganizationUsers200ResponseUsersInner.md) |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **project** | [**GetOrganizationUsers200ResponseUsersInnerProject**](GetOrganizationUsers200ResponseUsersInnerProject.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetProjectUsers200Response.new(
  users: null,
  total: null,
  project: null
)
```

