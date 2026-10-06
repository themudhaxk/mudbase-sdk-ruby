# Mudbase::GetUserOverview200ResponseFootprint

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_count** | **Integer** |  | [optional] |
| **storage_used** | **Integer** |  | [optional] |
| **session_count** | **Integer** |  | [optional] |
| **api_key_count** | **Integer** |  | [optional] |
| **collections_in_project** | **Integer** |  | [optional] |
| **collections** | [**Array&lt;GetOrganizationUsers200ResponseUsersInnerProject&gt;**](GetOrganizationUsers200ResponseUsersInnerProject.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetUserOverview200ResponseFootprint.new(
  file_count: null,
  storage_used: null,
  session_count: null,
  api_key_count: null,
  collections_in_project: null,
  collections: null
)
```

