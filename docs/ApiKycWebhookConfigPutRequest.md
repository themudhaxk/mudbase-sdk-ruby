# Mudbase::ApiKycWebhookConfigPutRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **webhook_url** | **String** | Destination URL. Send null or empty string to clear. | [optional] |
| **webhook_secret** | **String** | Explicit signing secret (min 16 chars). Send null or empty string to clear. | [optional] |
| **generate_secret** | **Boolean** | When true, the server generates a new secret and returns it once. | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::ApiKycWebhookConfigPutRequest.new(
  webhook_url: null,
  webhook_secret: null,
  generate_secret: null
)
```

