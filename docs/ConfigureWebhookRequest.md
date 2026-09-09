# Mudbase::ConfigureWebhookRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_url** | **String** | URL to receive webhook payloads; set to null or omit to disable | [optional] |
| **webhook_secret** | **String** | Optional secret for signing payloads (e.g. X-Webhook-Signature) | [optional] |
| **webhook_events** | **Array&lt;String&gt;** | Event types to send (e.g. collection.insert, collection.update) | [optional] |
| **webhook_version** | **String** | Version string for payload format | [optional] |
| **transformations** | [**Array&lt;GetWebhookConfig200ResponseDataTransformationsInner&gt;**](GetWebhookConfig200ResponseDataTransformationsInner.md) | Transformation rules to apply to payloads before delivery | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfigureWebhookRequest.new(
  webhook_url: null,
  webhook_secret: null,
  webhook_events: null,
  webhook_version: null,
  transformations: null
)
```

