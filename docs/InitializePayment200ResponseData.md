# Mudbase::InitializePayment200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **link** | **String** |  | [optional] |
| **tx_ref** | **String** |  | [optional] |
| **provider_ref** | **String** |  | [optional] |
| **amount** | **Float** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **org_receives** | **Float** | What the org nets after the single all-in Mudbase fee. | [optional] |
| **fee** | **Float** | The single all-in Mudbase fee, in the same currency as amount. | [optional] |
| **fee_rate** | **Float** | The effective fee rate applied (fee / amount). | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InitializePayment200ResponseData.new(
  link: null,
  tx_ref: null,
  provider_ref: null,
  amount: null,
  currency: null,
  org_receives: null,
  fee: null,
  fee_rate: null
)
```

