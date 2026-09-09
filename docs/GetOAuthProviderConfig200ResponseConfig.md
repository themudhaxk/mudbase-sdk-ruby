# Mudbase::GetOAuthProviderConfig200ResponseConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_id** | **String** |  | [optional] |
| **scope** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetOAuthProviderConfig200ResponseConfig.new(
  client_id: 123456789-abcdefghijklmnop.apps.googleusercontent.com,
  scope: [&quot;profile&quot;,&quot;email&quot;]
)
```

