# Mudbase::GetAvailableRoles200ResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **slug** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **signup_endpoint** | **String** |  | [optional] |
| **requires_approval** | **Boolean** |  | [optional] |
| **requires_payment** | **Boolean** |  | [optional] |
| **requires_kyc** | **Boolean** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetAvailableRoles200ResponseDataInner.new(
  slug: null,
  name: null,
  description: null,
  signup_endpoint: null,
  requires_approval: null,
  requires_payment: null,
  requires_kyc: null
)
```

