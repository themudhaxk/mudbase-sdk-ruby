# Mudbase::PatchProjectFcmConfigRequest

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'mudbase'

Mudbase::PatchProjectFcmConfigRequest.openapi_one_of
# =>
# [
#   :'PatchProjectFcmConfigRequestOneOf',
#   :'PatchProjectFcmConfigRequestOneOf1'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'mudbase'

Mudbase::PatchProjectFcmConfigRequest.build(data)
# => #<PatchProjectFcmConfigRequestOneOf:0x00007fdd4aab02a0>

Mudbase::PatchProjectFcmConfigRequest.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `PatchProjectFcmConfigRequestOneOf`
- `PatchProjectFcmConfigRequestOneOf1`
- `nil` (if no type matches)

