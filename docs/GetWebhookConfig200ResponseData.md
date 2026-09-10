# Mudbase::GetWebhookConfig200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_url** | **String** |  | [optional] |
| **webhook_events** | **Array&lt;String&gt;** |  | [optional] |
| **webhook_version** | **String** |  | [optional] |
| **transformations** | [**Array&lt;GetWebhookConfig200ResponseDataTransformationsInner&gt;**](GetWebhookConfig200ResponseDataTransformationsInner.md) | Transformation rules applied to payloads | [optional] |
| **has_secret** | **Boolean** | Whether a webhook secret is configured (value not returned) | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::GetWebhookConfig200ResponseData.new(
  webhook_url: null,
  webhook_events: null,
  webhook_version: null,
  transformations: null,
  has_secret: null
)
```

