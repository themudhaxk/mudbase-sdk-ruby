# Mudbase::UpdateFunctionRequestLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timeout** | **Integer** | Max execution time in ms (default 30000) | [optional] |
| **max_payload_size** | **Integer** | Max payload size in bytes (default 1MB) | [optional] |
| **max_executions_per_minute** | **Integer** |  | [optional] |
| **max_executions_per_hour** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateFunctionRequestLimits.new(
  timeout: null,
  max_payload_size: null,
  max_executions_per_minute: null,
  max_executions_per_hour: null
)
```

