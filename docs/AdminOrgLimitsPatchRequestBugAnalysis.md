# Mudbase::AdminOrgLimitsPatchRequestBugAnalysis

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **scans_per_month** | **Integer** |  | [optional] |
| **max_upload_bytes** | **Integer** |  | [optional] |
| **max_runtime_minutes** | **Integer** |  | [optional] |
| **queue_type** | **String** |  | [optional] |
| **log_retention_days** | **Integer** |  | [optional] |

## Example

```ruby
require 'mudbase'

instance = Mudbase::AdminOrgLimitsPatchRequestBugAnalysis.new(
  scans_per_month: null,
  max_upload_bytes: null,
  max_runtime_minutes: null,
  queue_type: null,
  log_retention_days: null
)
```

