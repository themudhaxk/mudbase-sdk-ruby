# Mudbase::UpdateMultiRoleSettingsRequestSettings

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **allow_multiple_roles** | **Boolean** | Whether an end user may hold multiple app roles. | [optional] |
| **require_role_selection** | **Boolean** | If true, signup must pick a role; if false and &#x60;autoAssignDefault&#x60; is true, &#x60;defaultRole&#x60; is used when omitted. | [optional] |
| **auto_assign_default** | **Boolean** | When true, assigns &#x60;defaultRole&#x60; when the client does not specify a role at signup. | [optional] |
| **data_owner_field** | **String** | Default document field for dataScope &#x60;own&#x60; (e.g. createdBy, userId). | [optional][default to &#39;createdBy&#39;] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateMultiRoleSettingsRequestSettings.new(
  allow_multiple_roles: null,
  require_role_selection: null,
  auto_assign_default: null,
  data_owner_field: null
)
```

