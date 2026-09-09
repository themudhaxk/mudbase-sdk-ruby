# Mudbase::FunctionLogsResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **executions** | [**Array&lt;FunctionExecution&gt;**](FunctionExecution.md) |  | [optional] |
| **stats** | [**FunctionStats**](FunctionStats.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::FunctionLogsResponseData.new(
  executions: null,
  stats: null
)
```

