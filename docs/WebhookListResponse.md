# Mudbase::WebhookListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhooks** | [**Array&lt;WebhookLog&gt;**](WebhookLog.md) |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **total_pages** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookListResponse.new(
  webhooks: null,
  total: null,
  page: null,
  limit: null,
  total_pages: null
)
```

