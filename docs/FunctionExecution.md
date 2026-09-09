# Mudbase::FunctionExecution

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | **String** |  | [optional] |
| **executed_at** | **Time** |  | [optional] |
| **execution_time** | **Integer** |  | [optional] |
| **success** | **Boolean** |  | [optional] |
| **payload** | **Object** |  | [optional] |
| **result** | **Object** |  | [optional] |
| **error** | **String** |  | [optional] |
| **trigger_type** | **String** |  | [optional] |
| **trigger_event** | **String** |  | [optional] |
| **invoked_by** | **String** |  | [optional] |
| **retry_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FunctionExecution.new(
  _id: null,
  executed_at: null,
  execution_time: null,
  success: null,
  payload: null,
  result: null,
  error: null,
  trigger_type: null,
  trigger_event: null,
  invoked_by: null,
  retry_count: null
)
```

