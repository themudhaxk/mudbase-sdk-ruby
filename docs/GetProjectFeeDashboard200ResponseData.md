# Mudbase::GetProjectFeeDashboard200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **fee_settings** | **Object** |  | [optional] |
| **balances** | [**Array&lt;GetProjectFeeDashboard200ResponseDataBalancesInner&gt;**](GetProjectFeeDashboard200ResponseDataBalancesInner.md) |  | [optional] |
| **recent_payouts** | [**Array&lt;GetProjectFeeDashboard200ResponseDataRecentPayoutsInner&gt;**](GetProjectFeeDashboard200ResponseDataRecentPayoutsInner.md) |  | [optional] |
| **total_earned** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetProjectFeeDashboard200ResponseData.new(
  fee_settings: null,
  balances: null,
  recent_payouts: null,
  total_earned: null
)
```

