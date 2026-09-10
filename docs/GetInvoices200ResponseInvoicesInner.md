# Mudbase::GetInvoices200ResponseInvoicesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **invoice_number** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **total** | **Float** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **due_date** | **Time** |  | [optional] |
| **paid_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **hosted_invoice_url** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetInvoices200ResponseInvoicesInner.new(
  _id: null,
  invoice_number: null,
  status: null,
  total: null,
  currency: null,
  due_date: null,
  paid_at: null,
  created_at: null,
  hosted_invoice_url: null
)
```

