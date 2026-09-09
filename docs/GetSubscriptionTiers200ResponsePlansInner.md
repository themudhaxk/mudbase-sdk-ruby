# Mudbase::GetSubscriptionTiers200ResponsePlansInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **price** | **Float** | Monthly price in cents | [optional] |
| **price_yearly** | **Float** | Yearly price in cents (2 months free, ~16.67% off) | [optional] |
| **currency** | **String** |  | [optional] |
| **price_id** | **String** |  | [optional] |
| **limits** | **Object** |  | [optional] |
| **overages** | **Object** |  | [optional] |
| **enforcement** | **Object** | Per-resource enforcement (blocking, billing_only, etc.) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetSubscriptionTiers200ResponsePlansInner.new(
  id: starter,
  name: Starter,
  description: null,
  price: 2900,
  price_yearly: null,
  currency: USD,
  price_id: null,
  limits: null,
  overages: null,
  enforcement: null
)
```

