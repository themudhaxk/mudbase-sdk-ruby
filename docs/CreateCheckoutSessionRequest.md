# Mudbase::CreateCheckoutSessionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan_id** | **String** | Plan ID to subscribe to |  |
| **billing_cycle** | **String** | Billing interval |  |
| **customer_info** | [**CreateCheckoutSessionRequestCustomerInfo**](CreateCheckoutSessionRequestCustomerInfo.md) |  |  |
| **success_url** | **String** | Redirect URL after successful payment | [optional] |
| **cancel_url** | **String** | Redirect URL if user cancels | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateCheckoutSessionRequest.new(
  plan_id: null,
  billing_cycle: null,
  customer_info: null,
  success_url: null,
  cancel_url: null
)
```

