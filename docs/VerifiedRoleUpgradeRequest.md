# Mudbase::VerifiedRoleUpgradeRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **target_role** | **String** |  |  |
| **payment_intent_id** | **String** | Payment intent ID from payment provider | [optional] |
| **verification_id** | **String** | KYC verification ID (if required) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::VerifiedRoleUpgradeRequest.new(
  target_role: seller,
  payment_intent_id: null,
  verification_id: null
)
```

