# Mudbase::CreateRoleRequestCollectionPermissionsValue

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'mudbase'

Mudbase::CreateRoleRequestCollectionPermissionsValue.openapi_one_of
# =>
# [
#   :'Array<CollectionAction>',
#   :'CollectionPermissionRule'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'mudbase'

Mudbase::CreateRoleRequestCollectionPermissionsValue.build(data)
# => #<Array<CollectionAction>:0x00007fdd4aab02a0>

Mudbase::CreateRoleRequestCollectionPermissionsValue.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `Array<CollectionAction>`
- `CollectionPermissionRule`
- `nil` (if no type matches)

