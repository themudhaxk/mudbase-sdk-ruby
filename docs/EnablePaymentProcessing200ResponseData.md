# Mudbase::EnablePaymentProcessing200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **onboarded** | **Boolean** |  | [optional] |
| **already_enabled** | **Boolean** |  | [optional] |
| **approval_status** | **String** | pending_review, approved, or rejected. Payments only start succeeding once this is approved, poll GET /payment-processing/status to track it. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EnablePaymentProcessing200ResponseData.new(
  onboarded: null,
  already_enabled: null,
  approval_status: null
)
```

