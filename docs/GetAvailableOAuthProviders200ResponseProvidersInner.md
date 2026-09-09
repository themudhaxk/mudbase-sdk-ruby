# Mudbase::GetAvailableOAuthProviders200ResponseProvidersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **strategy** | **String** |  | [optional] |
| **default_scope** | **Array&lt;String&gt;** |  | [optional] |
| **callback_url** | **String** |  | [optional] |
| **required_fields** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetAvailableOAuthProviders200ResponseProvidersInner.new(
  name: google,
  display_name: Google,
  strategy: google,
  default_scope: [&quot;profile&quot;,&quot;email&quot;],
  callback_url: /api/auth/oauth/callback/google,
  required_fields: [&quot;clientId&quot;,&quot;clientSecret&quot;]
)
```

