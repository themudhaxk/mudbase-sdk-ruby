# Mudbase::ConfigureWebhook200ResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_url** | **String** |  | [optional] |
| **webhook_events** | **Array&lt;String&gt;** |  | [optional] |
| **webhook_version** | **String** |  | [optional] |
| **transformations** | [**Array&lt;ConfigureWebhook200ResponseDataTransformationsInner&gt;**](ConfigureWebhook200ResponseDataTransformationsInner.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ConfigureWebhook200ResponseData.new(
  webhook_url: null,
  webhook_events: null,
  webhook_version: null,
  transformations: null
)
```

