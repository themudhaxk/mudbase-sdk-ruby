# Mudbase::WebhookLog

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** | MongoDB id — use as &#x60;webhookId&#x60; path param for retry | [optional] |
| **org** | **String** | Organization that owns the project | [optional] |
| **project** | **String** | Project id this delivery belongs to | [optional] |
| **webhook_id** | **String** | Internal correlation string (e.g. manual-173…), not the retry path id | [optional] |
| **url** | **String** |  | [optional] |
| **method** | **String** |  | [optional] |
| **event** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **payload** | **Object** | JSON body sent to your endpoint | [optional] |
| **headers** | **Object** | Outbound request headers (e.g. X-MUDBASE-Event, Content-Type) | [optional] |
| **response** | [**WebhookLogResponse**](WebhookLogResponse.md) |  | [optional] |
| **duration** | **Integer** | Round-trip time in milliseconds | [optional] |
| **attempts** | **Integer** |  | [optional] |
| **max_attempts** | **Integer** |  | [optional] |
| **error** | **String** |  | [optional] |
| **next_retry** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::WebhookLog.new(
  _id: null,
  org: null,
  project: null,
  webhook_id: null,
  url: null,
  method: null,
  event: null,
  status: null,
  payload: null,
  headers: null,
  response: null,
  duration: null,
  attempts: null,
  max_attempts: null,
  error: null,
  next_retry: null,
  created_at: null,
  updated_at: null
)
```

