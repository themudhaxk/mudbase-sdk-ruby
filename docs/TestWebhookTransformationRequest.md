# Mudbase::TestWebhookTransformationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **payload** | **Object** | Sample payload to transform |  |
| **transformations** | [**Array&lt;GetWebhookConfig200ResponseDataTransformationsInner&gt;**](GetWebhookConfig200ResponseDataTransformationsInner.md) | Transformation rules to apply |  |

## Example

```ruby
require 'mudbase'

instance = Mudbase::TestWebhookTransformationRequest.new(
  payload: null,
  transformations: null
)
```

