# Mudbase::CreateCheckoutSession200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **checkout_url** | **String** | Hosted payment URL (same as authorizationUrl) | [optional] |
| **authorization_url** | **String** | Hosted payment URL | [optional] |
| **access_code** | **String** | Gateway access code | [optional] |
| **reference** | **String** | Transaction reference (mudbase_...) for verify-payment | [optional] |
| **amount** | **Float** |  | [optional] |
| **currency** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateCheckoutSession200ResponseData.new(
  checkout_url: null,
  authorization_url: null,
  access_code: null,
  reference: null,
  amount: null,
  currency: null
)
```

