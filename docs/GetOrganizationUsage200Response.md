# Mudbase::GetOrganizationUsage200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **usage** | [**Usage**](Usage.md) |  | [optional] |
| **limits** | [**Limits**](Limits.md) |  | [optional] |
| **plan** | [**Plan**](Plan.md) |  | [optional] |
| **billing** | [**Billing**](Billing.md) |  | [optional] |
| **suborgs** | [**Array&lt;GetOrganizationUsage200ResponseAllOfSuborgsInner&gt;**](GetOrganizationUsage200ResponseAllOfSuborgsInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetOrganizationUsage200Response.new(
  usage: null,
  limits: null,
  plan: null,
  billing: null,
  suborgs: null
)
```

