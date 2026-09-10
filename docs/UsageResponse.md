# Mudbase::UsageResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **usage** | [**Usage**](Usage.md) |  | [optional] |
| **limits** | [**Limits**](Limits.md) |  | [optional] |
| **plan** | [**Plan**](Plan.md) |  | [optional] |
| **billing** | [**Billing**](Billing.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UsageResponse.new(
  usage: null,
  limits: null,
  plan: null,
  billing: null
)
```

