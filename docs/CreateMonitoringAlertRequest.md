# Mudbase::CreateMonitoringAlertRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **condition** | **String** |  | [optional] |
| **threshold** | **Float** |  | [optional] |
| **action** | **String** |  | [optional] |
| **project_id** | **String** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::CreateMonitoringAlertRequest.new(
  name: null,
  condition: null,
  threshold: null,
  action: null,
  project_id: null
)
```

