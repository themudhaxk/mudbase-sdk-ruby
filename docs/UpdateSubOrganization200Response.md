# Mudbase::UpdateSubOrganization200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **org** | [**Organization**](Organization.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateSubOrganization200Response.new(
  message: Sub-organization updated successfully,
  org: null
)
```

