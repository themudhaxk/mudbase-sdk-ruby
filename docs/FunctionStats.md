# Mudbase::FunctionStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_executions** | **Integer** |  | [optional] |
| **successful_executions** | **Integer** |  | [optional] |
| **failed_executions** | **Integer** |  | [optional] |
| **avg_execution_time** | **Float** |  | [optional] |
| **last_execution** | **Time** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FunctionStats.new(
  total_executions: null,
  successful_executions: null,
  failed_executions: null,
  avg_execution_time: null,
  last_execution: null
)
```

