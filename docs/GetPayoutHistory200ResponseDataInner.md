# Mudbase::GetPayoutHistory200ResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **gross_amount** | **Float** |  | [optional] |
| **network_fee** | **Float** |  | [optional] |
| **net_amount** | **Float** |  | [optional] |
| **to_address** | **String** |  | [optional] |
| **tx_hash** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPayoutHistory200ResponseDataInner.new(
  _id: null,
  currency: null,
  gross_amount: null,
  network_fee: null,
  net_amount: null,
  to_address: null,
  tx_hash: null,
  status: null,
  created_at: null
)
```

