# Mudbase::UpdateOrganizationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **logo** | **String** | Optional logo URL. Not used for emails (org emails use platform logo). | [optional] |
| **website** | **String** |  | [optional] |
| **settings** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateOrganizationRequest.new(
  name: null,
  description: null,
  logo: null,
  website: null,
  settings: null
)
```

