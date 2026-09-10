# Mudbase::CreateOrUpdateFeeSettingsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **currency** | **String** |  |  |
| **enabled** | **Boolean** |  | [optional] |
| **fee_amount** | **Float** |  | [optional] |
| **payout_address** | **String** |  | [optional] |
| **payout_threshold** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateOrUpdateFeeSettingsRequest.new(
  currency: null,
  enabled: null,
  fee_amount: null,
  payout_address: null,
  payout_threshold: null
)
```

