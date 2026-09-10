# Mudbase::Permission

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **role** | **String** |  | [optional] |
| **actions** | **Array&lt;String&gt;** |  | [optional] |
| **fields** | **Array&lt;String&gt;** |  | [optional] |
| **condition** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Permission.new(
  role: null,
  actions: null,
  fields: null,
  condition: null
)
```

