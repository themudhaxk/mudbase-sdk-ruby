# Mudbase::GetBillingEstimate200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **period** | **String** | Current month YYYY-MM | [optional] |
| **line_items** | [**Array&lt;GetBillingEstimate200ResponseLineItemsInner&gt;**](GetBillingEstimate200ResponseLineItemsInner.md) |  | [optional] |
| **estimated_overage_cents** | **Float** |  | [optional] |
| **estimated_overage** | **String** |  | [optional] |
| **forecast_overage_cents** | **Float** |  | [optional] |
| **forecast_overage** | **String** |  | [optional] |
| **message** | **String** | Human-readable forecast when applicable | [optional] |
| **spend_limits** | [**GetBillingEstimate200ResponseSpendLimits**](GetBillingEstimate200ResponseSpendLimits.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetBillingEstimate200Response.new(
  period: null,
  line_items: null,
  estimated_overage_cents: null,
  estimated_overage: $12.50,
  forecast_overage_cents: null,
  forecast_overage: $38.00,
  message: null,
  spend_limits: null
)
```

