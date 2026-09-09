# Mudbase::UpdateCurrencyFeeSettingsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **fee_amount** | **Float** |  | [optional] |
| **payout_address** | **String** |  | [optional] |
| **payout_threshold** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateCurrencyFeeSettingsRequest.new(
  enabled: null,
  fee_amount: null,
  payout_address: null,
  payout_threshold: null
)
```

