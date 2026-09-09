# Mudbase::ApiKycWebhookConfigPut200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_url** | **String** |  | [optional] |
| **secret_set** | **Boolean** |  | [optional] |
| **webhook_secret** | **String** | Only present when generateSecret was true. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiKycWebhookConfigPut200Response.new(
  webhook_url: null,
  secret_set: null,
  webhook_secret: null
)
```

