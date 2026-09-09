# Mudbase::McpConfigGet200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **plan** | **String** |  | [optional] |
| **allowed_plans** | **Array&lt;String&gt;** |  | [optional] |
| **free_promo_active** | **Boolean** | True if this org is on the free plan and MCP is temporarily enabled via the launch promo | [optional] |
| **free_promo_ends_at** | **Time** | When the free-plan MCP promo ends (null if not active) | [optional] |
| **endpoint** | **String** |  | [optional] |
| **tools** | [**Array&lt;McpConfigGet200ResponseToolsInner&gt;**](McpConfigGet200ResponseToolsInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::McpConfigGet200Response.new(
  enabled: null,
  plan: null,
  allowed_plans: null,
  free_promo_active: null,
  free_promo_ends_at: null,
  endpoint: null,
  tools: null
)
```

