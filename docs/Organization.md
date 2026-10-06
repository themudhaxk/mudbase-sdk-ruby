# Mudbase::Organization

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **logo** | **String** | Optional logo URL. Org-related emails use the platform logo (env); this field is for legacy or future UI use only. | [optional] |
| **website** | **String** |  | [optional] |
| **plan** | [**Plan**](Plan.md) |  | [optional] |
| **usage** | [**Usage**](Usage.md) |  | [optional] |
| **limits** | [**Limits**](Limits.md) |  | [optional] |
| **billing** | [**Billing**](Billing.md) |  | [optional] |
| **settings** | **Object** | May include customDomainAddon (optional billing/legacy flag; not required for custom domains on Growth/Scale). | [optional] |
| **deployment_type** | **String** |  | [optional] |
| **dedicated** | **Object** | Dedicated API/DB routing; may include edgeTlsStatus, infraMeteringLastReportAt. | [optional] |
| **preferred_region** | **String** |  | [optional] |
| **infrastructure_environments** | **Array&lt;Object&gt;** |  | [optional] |
| **allowed_domains** | **Array&lt;Object&gt;** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Organization.new(
  _id: null,
  name: null,
  slug: null,
  description: null,
  logo: null,
  website: null,
  plan: null,
  usage: null,
  limits: null,
  billing: null,
  settings: null,
  deployment_type: null,
  dedicated: null,
  preferred_region: null,
  infrastructure_environments: null,
  allowed_domains: null,
  created_at: null,
  updated_at: null
)
```

