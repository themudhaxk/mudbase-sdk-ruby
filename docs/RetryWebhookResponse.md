# Mudbase::RetryWebhookResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message** | **String** |  |  |
| **webhook_id** | **String** | Same log _id you passed in the path |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::RetryWebhookResponse.new(
  message: Webhook retry initiated,
  webhook_id: null
)
```

