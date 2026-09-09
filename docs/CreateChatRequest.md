# Mudbase::CreateChatRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **type** | **String** |  |  |
| **participants** | **Array&lt;String&gt;** |  |  |
| **settings** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateChatRequest.new(
  name: null,
  description: null,
  type: null,
  participants: null,
  settings: null
)
```

