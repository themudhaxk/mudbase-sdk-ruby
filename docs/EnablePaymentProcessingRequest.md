# Mudbase::EnablePaymentProcessingRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_bank** | **String** | Bank code (from GET /v3/banks/{country}) |  |
| **account_number** | **String** | Org bank account number |  |
| **country** | **String** | Country code (e.g. US, NG) |  |
| **business_name** | **String** |  |  |
| **business_mobile** | **String** |  | [optional] |
| **bvn** | **String** | Required only when country is NG (Nigeria) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EnablePaymentProcessingRequest.new(
  account_bank: null,
  account_number: null,
  country: null,
  business_name: null,
  business_mobile: null,
  bvn: null
)
```

