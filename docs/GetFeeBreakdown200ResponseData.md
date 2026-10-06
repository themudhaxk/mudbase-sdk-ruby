# Mudbase::GetFeeBreakdown200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **amount** | **Float** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **org_receives** | **Float** |  | [optional] |
| **fee** | **Float** | The single all-in Mudbase fee. | [optional] |
| **fee_rate** | **Float** | The effective fee rate applied (fee / amount). | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetFeeBreakdown200ResponseData.new(
  amount: null,
  currency: null,
  org_receives: null,
  fee: null,
  fee_rate: null
)
```

