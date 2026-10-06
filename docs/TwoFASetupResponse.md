# Mudbase::TwoFASetupResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **secret** | **String** |  | [optional] |
| **qr_code** | **String** |  | [optional] |
| **manual_entry_key** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::TwoFASetupResponse.new(
  secret: null,
  qr_code: null,
  manual_entry_key: null
)
```

