# Mudbase::GetPaymentProcessingStatus200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **onboarded** | **Boolean** |  | [optional] |
| **enabled** | **Boolean** | Whether payment collection is actually toggled on (implies approved). | [optional] |
| **approval_status** | **String** | not_submitted, pending_review, approved, or rejected. | [optional] |
| **status** | **String** | Derived overall status for the console to render: not_onboarded, pending_review, rejected, disabled, or active. | [optional] |
| **rejection_reason** | **String** |  | [optional] |
| **stablecoin** | [**GetPaymentProcessingStatus200ResponseDataStablecoin**](GetPaymentProcessingStatus200ResponseDataStablecoin.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPaymentProcessingStatus200ResponseData.new(
  onboarded: null,
  enabled: null,
  approval_status: null,
  status: null,
  rejection_reason: null,
  stablecoin: null
)
```

