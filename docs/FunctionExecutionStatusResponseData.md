# Mudbase::FunctionExecutionStatusResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **execution_id** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **duration_ms** | **Integer** | Duration in milliseconds (null until completed) | [optional] |
| **result** | **Object** |  | [optional] |
| **error** | **String** |  | [optional] |
| **error_class** | **String** |  | [optional] |
| **logs** | [**FunctionExecutionStatusResponseDataLogs**](FunctionExecutionStatusResponseDataLogs.md) |  | [optional] |
| **machine** | **Object** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **started_at** | **Time** |  | [optional] |
| **completed_at** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FunctionExecutionStatusResponseData.new(
  execution_id: null,
  status: null,
  duration_ms: null,
  result: null,
  error: null,
  error_class: null,
  logs: null,
  machine: null,
  created_at: null,
  started_at: null,
  completed_at: null
)
```

