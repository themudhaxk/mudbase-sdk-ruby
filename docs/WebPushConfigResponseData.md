# Mudbase::WebPushConfigResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** | Whether native Web Push is enabled for this project. | [optional] |
| **has_keys** | **Boolean** | Whether a VAPID keypair has been provisioned. | [optional] |
| **public_key** | **String** | The VAPID application-server public key clients subscribe with. Null when native Web Push is not enabled.  | [optional] |
| **vapid_subject** | **String** | RFC 8292 contact subject (a &#x60;mailto:&#x60; address or &#x60;https&#x60; URL). | [optional] |
| **generated_at** | **Time** | When the current VAPID keypair was generated. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebPushConfigResponseData.new(
  enabled: null,
  has_keys: null,
  public_key: null,
  vapid_subject: null,
  generated_at: null
)
```

