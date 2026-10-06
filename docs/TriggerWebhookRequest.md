# Mudbase::TriggerWebhookRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **String** | Target project (must belong to your org) |  |
| **url** | **String** | HTTPS URL validated against SSRF rules |  |
| **event** | **String** | Event name (sent as X-MUDBASE-Event) |  |
| **payload** | **Object** | JSON body POSTed to your endpoint |  |
| **method** | **String** |  | [optional][default to &#39;POST&#39;] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::TriggerWebhookRequest.new(
  project_id: null,
  url: null,
  event: null,
  payload: null,
  method: null
)
```

