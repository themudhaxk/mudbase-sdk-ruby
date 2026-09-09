# Mudbase::ListOAuthProviders200ResponseProvidersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  | [optional] |
| **provider_id** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **linked_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ListOAuthProviders200ResponseProvidersInner.new(
  provider: google,
  provider_id: google-user-id-123,
  email: user@gmail.com,
  linked_at: null
)
```

