# Mudbase::ConfigureOAuthProvider200ResponseProvider

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **enabled** | **Boolean** |  | [optional] |
| **display_name** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfigureOAuthProvider200ResponseProvider.new(
  name: google,
  enabled: true,
  display_name: Sign in with Google
)
```

