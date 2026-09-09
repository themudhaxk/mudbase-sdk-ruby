# Mudbase::UpdateOAuthProviderConfigRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** | Whether the OAuth provider is enabled | [optional] |
| **client_id** | **String** | OAuth client ID from the provider | [optional] |
| **client_secret** | **String** | OAuth client secret from the provider | [optional] |
| **scope** | **Array&lt;String&gt;** | OAuth scopes to request | [optional] |
| **display_name** | **String** | Custom display name for the provider | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateOAuthProviderConfigRequest.new(
  enabled: true,
  client_id: 123456789-abcdefghijklmnop.apps.googleusercontent.com,
  client_secret: GOCSPX-abcdefghijklmnopqrstuvwxyz,
  scope: [&quot;profile&quot;,&quot;email&quot;],
  display_name: Sign in with Google
)
```

