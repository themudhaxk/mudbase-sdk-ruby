# Mudbase::InitializePaymentRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **amount** | **Float** | Payment amount (e.g. USD) |  |
| **currency** | **String** |  | [optional][default to &#39;USD&#39;] |
| **project_id** | **String** | Optional project scope | [optional] |
| **customer** | [**InitializePaymentRequestCustomer**](InitializePaymentRequestCustomer.md) |  |  |
| **metadata** | **Object** | title, description, redirectUrl, etc. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InitializePaymentRequest.new(
  amount: null,
  currency: null,
  project_id: null,
  customer: null,
  metadata: null
)
```

