# Mudbase::GetPayoutBanks200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **banks_list_supported** | **Boolean** |  | [optional] |
| **banks** | [**Array&lt;GetPayoutBanks200ResponseDataBanksInner&gt;**](GetPayoutBanks200ResponseDataBanksInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetPayoutBanks200ResponseData.new(
  banks_list_supported: null,
  banks: null
)
```

