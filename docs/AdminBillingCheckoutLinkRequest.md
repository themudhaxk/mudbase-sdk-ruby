# Mudbase::AdminBillingCheckoutLinkRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan** | **String** |  |  |
| **billing_cycle** | **String** |  | [optional][default to &#39;monthly&#39;] |
| **amount_cents** | **Integer** | Monthly amount in cents (overrides catalog; enterprise default is contract) | [optional] |
| **charge_amount_cents** | **Integer** | Exact charge in cents for this checkout (overrides monthly math) | [optional] |
| **currency** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **redirect_url** | **String** |  | [optional] |
| **send_email** | **Boolean** |  | [optional][default to false] |
| **to_email** | **String** |  | [optional] |
| **message** | **String** | Optional note shown in org_billing_checkout email | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AdminBillingCheckoutLinkRequest.new(
  plan: null,
  billing_cycle: null,
  amount_cents: null,
  charge_amount_cents: null,
  currency: null,
  email: null,
  name: null,
  redirect_url: null,
  send_email: null,
  to_email: null,
  message: null
)
```

