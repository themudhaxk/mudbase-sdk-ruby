# Mudbase::SystemStatusResponseData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **uptime** | **Integer** |  | [optional] |
| **memory** | [**SystemStatusResponseDataMemory**](SystemStatusResponseDataMemory.md) |  | [optional] |
| **cpu** | [**SystemStatusResponseDataCpu**](SystemStatusResponseDataCpu.md) |  | [optional] |
| **requests** | [**SystemStatusResponseDataRequests**](SystemStatusResponseDataRequests.md) |  | [optional] |
| **database** | [**SystemStatusResponseDataDatabase**](SystemStatusResponseDataDatabase.md) |  | [optional] |
| **storage** | [**SystemStatusResponseDataStorage**](SystemStatusResponseDataStorage.md) |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::SystemStatusResponseData.new(
  uptime: null,
  memory: null,
  cpu: null,
  requests: null,
  database: null,
  storage: null
)
```

