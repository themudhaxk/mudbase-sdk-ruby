# Mudbase::Limits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **projects** | **Integer** |  | [optional] |
| **users** | **Integer** |  | [optional] |
| **storage** | **Integer** |  | [optional] |
| **bandwidth** | **Integer** |  | [optional] |
| **api_calls** | **Integer** |  | [optional] |
| **db_reads** | **Integer** |  | [optional] |
| **db_writes** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::Limits.new(
  projects: null,
  users: null,
  storage: null,
  bandwidth: null,
  api_calls: null,
  db_reads: null,
  db_writes: null
)
```

