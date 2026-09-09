# Mudbase::WebhookLogResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **Integer** | HTTP status code from your endpoint | [optional] |
| **body** | **Object** | Parsed JSON when possible; otherwise structure varies | [optional] |
| **headers** | **Object** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookLogResponse.new(
  status: null,
  body: null,
  headers: null
)
```

