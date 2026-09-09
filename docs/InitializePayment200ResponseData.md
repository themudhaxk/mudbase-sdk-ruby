# Mudbase::InitializePayment200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **link** | **String** |  | [optional] |
| **tx_ref** | **String** |  | [optional] |
| **provider_ref** | **String** |  | [optional] |
| **amount** | **Float** |  | [optional] |
| **currency** | **String** |  | [optional] |
| **org_receives** | **Float** |  | [optional] |
| **platform_percent** | **Float** |  | [optional] |
| **platform_fixed** | **Float** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::InitializePayment200ResponseData.new(
  link: null,
  tx_ref: null,
  provider_ref: null,
  amount: null,
  currency: null,
  org_receives: null,
  platform_percent: null,
  platform_fixed: null
)
```

