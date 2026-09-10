# Mudbase::ConfigureOAuthProvider200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  | [optional] |
| **provider** | [**ConfigureOAuthProvider200ResponseProvider**](ConfigureOAuthProvider200ResponseProvider.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfigureOAuthProvider200Response.new(
  message: google OAuth configuration updated,
  provider: null
)
```

