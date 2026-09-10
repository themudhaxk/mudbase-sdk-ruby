# Mudbase::GetOrgOAuthProviders200ResponseProvidersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **strategy** | **String** |  | [optional] |
| **default_scope** | **Array&lt;String&gt;** |  | [optional] |
| **auth_url** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetOrgOAuthProviders200ResponseProvidersInner.new(
  name: google,
  display_name: Google,
  strategy: google,
  default_scope: [&quot;profile&quot;,&quot;email&quot;],
  auth_url: /api/auth/oauth-org/google
)
```

