# Mudbase::GetPaymentRecords200ResponseDataRecordsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tx_ref** | **String** |  | [optional] |
| **amount** | **Float** |  | [optional] |
| **org_receives** | **Float** |  | [optional] |
| **status** | **String** |  | [optional] |
| **paid_at** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPaymentRecords200ResponseDataRecordsInner.new(
  tx_ref: null,
  amount: null,
  org_receives: null,
  status: null,
  paid_at: null
)
```

