# Mudbase::ExportUserData200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **exported_at** | **Time** |  | [optional] |
| **user** | [**User**](User.md) |  | [optional] |
| **projects** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **wallets** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **transactions** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **files** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **integrations** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |
| **api_keys** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ExportUserData200Response.new(
  exported_at: null,
  user: null,
  projects: null,
  wallets: null,
  transactions: null,
  files: null,
  integrations: null,
  api_keys: null
)
```

