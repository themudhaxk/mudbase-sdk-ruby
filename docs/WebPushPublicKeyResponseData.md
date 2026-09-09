# Mudbase::WebPushPublicKeyResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **public_key** | **String** | The VAPID application-server public key, or null when native Web Push is not enabled.  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushPublicKeyResponseData.new(
  enabled: null,
  public_key: null
)
```

