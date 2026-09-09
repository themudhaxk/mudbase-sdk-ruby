# Mudbase::InitializeOrgPlanCheckout200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **link** | **String** | Payment URL | [optional] |
| **tx_ref** | **String** | Reference for verify-payment (mudbase_org_...) | [optional] |
| **provider_ref** | **String** |  | [optional] |
| **billing_cycle** | **String** |  | [optional] |
| **amount** | **Float** |  | [optional] |
| **amount_cents** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InitializeOrgPlanCheckout200ResponseData.new(
  link: null,
  tx_ref: null,
  provider_ref: null,
  billing_cycle: null,
  amount: null,
  amount_cents: null
)
```

