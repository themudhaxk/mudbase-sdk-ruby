# Mudbase::GetOAuthProviderConfig200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **enabled** | **Boolean** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **config** | [**GetOAuthProviderConfig200ResponseConfig**](GetOAuthProviderConfig200ResponseConfig.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetOAuthProviderConfig200Response.new(
  name: google,
  enabled: true,
  display_name: Sign in with Google,
  config: null
)
```

