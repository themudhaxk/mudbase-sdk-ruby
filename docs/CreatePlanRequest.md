# Mudbase::CreatePlanRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | Display name; also used to generate a unique slug per project. |  |
| **description** | **String** |  | [optional] |
| **price** | **Float** | Amount for the chosen interval. The server fills the other billing period (e.g. yearly ≈ monthly × 12 × 0.8 when interval is month).  |  |
| **currency** | **String** | ISO currency code (stored lowercased). |  |
| **interval** | **String** | Which period &#x60;price&#x60; applies to; drives pricing.monthly vs pricing.yearly. |  |
| **features** | [**Array&lt;CreatePlanRequestFeaturesInner&gt;**](CreatePlanRequestFeaturesInner.md) | Strings become &#x60;{ name, included: true }&#x60;. You may send full feature objects instead.  | [optional] |
| **limits** | [**CreatePlanRequestLimits**](CreatePlanRequestLimits.md) |  | [optional] |
| **trial** | [**CreatePlanRequestTrial**](CreatePlanRequestTrial.md) |  | [optional] |
| **is_active** | **Boolean** |  | [optional][default to true] |
| **is_default** | **Boolean** | Only one default plan per project is allowed server-side. | [optional][default to false] |
| **sort_order** | **Float** | Lower numbers list first in UIs. | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** | Arbitrary key/value data stored on the plan document. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreatePlanRequest.new(
  name: null,
  description: null,
  price: null,
  currency: USD,
  interval: null,
  features: null,
  limits: null,
  trial: null,
  is_active: null,
  is_default: null,
  sort_order: null,
  metadata: null
)
```

