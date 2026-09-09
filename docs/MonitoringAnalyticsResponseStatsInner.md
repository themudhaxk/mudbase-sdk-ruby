# Mudbase::MonitoringAnalyticsResponseStatsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **String** |  | [optional] |
| **api_calls** | **Integer** |  | [optional] |
| **db_reads** | **Integer** |  | [optional] |
| **db_writes** | **Integer** |  | [optional] |
| **storage** | **Integer** |  | [optional] |
| **bandwidth** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::MonitoringAnalyticsResponseStatsInner.new(
  date: null,
  api_calls: null,
  db_reads: null,
  db_writes: null,
  storage: null,
  bandwidth: null
)
```

