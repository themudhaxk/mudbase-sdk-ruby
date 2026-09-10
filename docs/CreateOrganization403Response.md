# Mudbase::CreateOrganization403Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error** | **String** |  | [optional] |
| **code** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateOrganization403Response.new(
  error: Creating organizations via API is disabled.,
  code: ORG_CREATION_DISABLED
)
```

