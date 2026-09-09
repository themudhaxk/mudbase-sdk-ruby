# Mudbase::UpdateMultiRoleSettingsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **is_enabled** | **Boolean** |  | [optional] |
| **default_role** | **String** |  | [optional] |
| **settings** | [**UpdateMultiRoleSettingsRequestSettings**](UpdateMultiRoleSettingsRequestSettings.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateMultiRoleSettingsRequest.new(
  is_enabled: true,
  default_role: customer,
  settings: null
)
```

