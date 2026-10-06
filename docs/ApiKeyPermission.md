# Mudbase::ApiKeyPermission

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **resource** | **String** | Resource scope for this permission (auth, database, storage, functions, realtime, messaging) |  |
| **actions** | **Array&lt;String&gt;** | Allowed actions on the resource |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiKeyPermission.new(
  resource: null,
  actions: null
)
```

