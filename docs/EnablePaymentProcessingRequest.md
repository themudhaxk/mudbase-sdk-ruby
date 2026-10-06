# Mudbase::EnablePaymentProcessingRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country** | **String** | ISO-3166 alpha-2 payout country code, one of the codes returned by GET /payment-processing/countries (e.g. NG, GH, KE, US, GB). |  |
| **business_name** | **String** |  |  |
| **business_mobile** | **String** | Optional, used for payout provider account notifications. | [optional] |
| **account_bank** | **String** | Bank code, mobile-money network code, routing number, or sort code, depending on country. | [optional] |
| **account_number** | **String** | Bank/mobile-money account number, IBAN, or similar, depending on country. | [optional] |
| **bvn** | **String** | Required only when country is NG (Nigeria). | [optional] |
| **account_type** | **String** | Required only when country is US (checking or savings). | [optional] |
| **account_holder_name** | **String** | Required only when country is US or GB. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::EnablePaymentProcessingRequest.new(
  country: null,
  business_name: null,
  business_mobile: null,
  account_bank: null,
  account_number: null,
  bvn: null,
  account_type: null,
  account_holder_name: null
)
```

