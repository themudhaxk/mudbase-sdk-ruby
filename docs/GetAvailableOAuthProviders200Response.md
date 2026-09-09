# Mudbase::GetAvailableOAuthProviders200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **providers** | [**Array&lt;GetAvailableOAuthProviders200ResponseProvidersInner&gt;**](GetAvailableOAuthProviders200ResponseProvidersInner.md) |  | [optional] |
| **total** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetAvailableOAuthProviders200Response.new(
  providers: null,
  total: 29
)
```

