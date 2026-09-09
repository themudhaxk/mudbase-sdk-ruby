# Mudbase::ConfigureOAuthProviderRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** | Whether the OAuth provider is enabled |  |
| **client_id** | **String** | OAuth client ID from the provider |  |
| **client_secret** | **String** | OAuth client secret from the provider |  |
| **scope** | **Array&lt;String&gt;** | OAuth scopes to request | [optional] |
| **display_name** | **String** | Custom display name for the provider | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfigureOAuthProviderRequest.new(
  enabled: true,
  client_id: 123456789-abcdefghijklmnop.apps.googleusercontent.com,
  client_secret: GOCSPX-abcdefghijklmnopqrstuvwxyz,
  scope: [&quot;profile&quot;,&quot;email&quot;],
  display_name: Sign in with Google
)
```

