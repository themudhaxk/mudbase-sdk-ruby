# Mudbase::SimulateFunctionTriggerRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **trigger** | **Object** | Simulated trigger (type, event) | [optional] |
| **event_context** | **Object** | Simulated event context (document, file, webhook, message) | [optional] |
| **payload** | **Object** | Additional payload | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SimulateFunctionTriggerRequest.new(
  trigger: null,
  event_context: null,
  payload: null
)
```

