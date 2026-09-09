# Mudbase::AdminOrgBillingContractPatchRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **contract_amount_cents** | **Integer** |  | [optional] |
| **contract_currency** | **String** |  | [optional] |
| **contract_billing_interval** | **String** |  | [optional] |
| **contract_effective_from** | **Time** |  | [optional] |
| **contract_notes** | **String** |  | [optional] |
| **reason** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AdminOrgBillingContractPatchRequest.new(
  contract_amount_cents: null,
  contract_currency: null,
  contract_billing_interval: null,
  contract_effective_from: null,
  contract_notes: null,
  reason: null
)
```

