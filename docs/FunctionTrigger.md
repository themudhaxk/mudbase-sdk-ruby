# Mudbase::FunctionTrigger

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** | Trigger type |  |
| **event** | **String** | Event name (e.g. create, update, delete for document; uploaded, deleted for file) | [optional] |
| **schedule** | **String** | For cron - minutely, hourly, daily, weekly, or custom cron expression | [optional] |
| **path** | **String** | HTTP path for http triggers | [optional] |
| **method** | **String** |  | [optional] |
| **collection_id** | **String** | For document triggers - filter by collection | [optional] |
| **bucket_id** | **String** | For file triggers - filter by bucket | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FunctionTrigger.new(
  type: null,
  event: null,
  schedule: null,
  path: null,
  method: null,
  collection_id: null,
  bucket_id: null
)
```

