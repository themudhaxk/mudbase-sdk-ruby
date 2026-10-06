# Mudbase::UpdateFunctionRequestRetryPolicy

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  | [optional] |
| **max_retries** | **Integer** |  | [optional] |
| **backoff_ms** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::UpdateFunctionRequestRetryPolicy.new(
  enabled: null,
  max_retries: null,
  backoff_ms: null
)
```

