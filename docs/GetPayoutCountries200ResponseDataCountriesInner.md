# Mudbase::GetPayoutCountries200ResponseDataCountriesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** | ISO-3166 alpha-2 country code (e.g. NG, GH, KE, US, GB). | [optional] |
| **name** | **String** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **banks_list_supported** | **Boolean** | Whether GET /payment-processing/banks returns a live bank list for this country. | [optional] |
| **mobile_money** | **Boolean** |  | [optional] |
| **international** | **Boolean** | True for a market whose settlement rail requires an account-level capability beyond the standard local-rail onboarding (currently US, GB). | [optional] |
| **fields** | [**Array&lt;GetPayoutCountries200ResponseDataCountriesInnerFieldsInner&gt;**](GetPayoutCountries200ResponseDataCountriesInnerFieldsInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPayoutCountries200ResponseDataCountriesInner.new(
  code: null,
  name: null,
  currency: null,
  banks_list_supported: null,
  mobile_money: null,
  international: null,
  fields: null
)
```

