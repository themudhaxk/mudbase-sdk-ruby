# Mudbase::CreateApiKey400Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error** | **String** |  | [optional] |
| **details** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateApiKey400Response.new(
  error: Validation failed,
  details: [&quot;\&quot;permissions[0]\&quot; must be of type object&quot;,&quot;\&quot;expiresAt\&quot; must be a valid date&quot;]
)
```

