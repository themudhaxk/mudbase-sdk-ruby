# Mudbase::UpdateOrganization200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **org** | [**Organization**](Organization.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateOrganization200Response.new(
  message: Organization updated successfully,
  org: null
)
```

