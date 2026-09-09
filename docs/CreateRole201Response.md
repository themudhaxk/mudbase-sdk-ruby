# Mudbase::CreateRole201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **role** | [**CreateRole201ResponseRole**](CreateRole201ResponseRole.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateRole201Response.new(
  message: Role created successfully,
  role: null
)
```

