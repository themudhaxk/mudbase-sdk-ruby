# Mudbase::GetProjectOAuthProviders200ResponseProvidersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **display_name** | **String** |  | [optional] |
| **auth_url** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetProjectOAuthProviders200ResponseProvidersInner.new(
  name: google,
  display_name: Sign in with Google,
  auth_url: /api/auth/oauth/google?projectId&#x3D;685ad30be129932fbb7a1047
)
```

