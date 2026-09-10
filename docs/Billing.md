# Mudbase::Billing

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **next_billing_date** | **Time** |  | [optional] |
| **payment_method** | **String** |  | [optional] |
| **last_payment** | [**BillingLastPayment**](BillingLastPayment.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Billing.new(
  next_billing_date: null,
  payment_method: null,
  last_payment: null
)
```

