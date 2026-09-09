# Mudbase::UsageTrendsResponseTrendsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_id** | [**UsageTrendsResponseTrendsInnerId**](UsageTrendsResponseTrendsInnerId.md) |  | [optional] |
| **api_calls** | **Integer** |  | [optional] |
| **storage** | **Integer** |  | [optional] |
| **bandwidth** | **Integer** |  | [optional] |
| **db_reads** | **Integer** |  | [optional] |
| **db_writes** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UsageTrendsResponseTrendsInner.new(
  _id: null,
  api_calls: null,
  storage: null,
  bandwidth: null,
  db_reads: null,
  db_writes: null
)
```

